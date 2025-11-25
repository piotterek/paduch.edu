# Jak udostępnić usługę przez cloudflare tunnel
1. wejdź na https://dash.cloudflare.com/
2.  z menu wybierz 'Zero trust'
3.  w nowym menu wybierz 'Network' > 'Connectors'
4.  wybierz:
	- Jeśli nie masz skonfigurowanego tunelu 'Create a tunnel'
	- Jeśli masz już jakiś tunel, wybierz go z listy
5. w oknie które pojawi się z prawej strony kliknij 'Edit'
6.  na pasku opcji na górze wybierz 'Published application routes'
7.  kliknij 'Add a published application route'
8.  Podaj potrzebne dane:
	- Subdomain (opcjonalnie) - podaj sufix poprzedzający domenę
	- Domain - podaj domenę przez którą ma być udostępniona usługa
	- Path (opcjonalnie) - podaj to co ma być dodane w padsku url po domenie (zostanie dodane po adresie url podanym niżej) Ogólnie nie polecam - brzydko wygląda, a później skonfigurujemy przekierowanie
	- Type - typ połącznia np. HTTP, SSH, TCP
	- URL - wewnętrzny adres url na którym jest usługa ale tylko IP oraz opcjonalnie port
9.  Zapisz klikając 'Save'
10.  przejdż z powrotem do głównego dashboardu (najprościej klikają logo cloudflare w lewym górnym rogu)
11.  wybierz z listy domenę przez którą jest udostępniona usługa
12.  w menu wybierz 'Rules' > 'Page Rules'
13.  kliknij 'Create Page Rule'
14. Uzupełnij dane: 
	- URL - adrs który podałeś w konfiguracji połączenia (subdomain + domain)
	- Pick a setting - wybierz z listy 'Redirect URL'
	- Po prawej stronie pola 'Pick a setting' pojawi się nowe - 'Select status code' - wybierz z listy kod 301
	- Enter destination URL - podaj adres do którego ma być przekierowanie
15.  zapisz klikając 'Save and Deploy Page Rule'

---

# Przykład - udostępnienie strony statusu Uptime Kuma

Strona w LAN jest dostępna pod: http://10.0.0.201:3001/status/homelab

1. W konfiguracji tunela mam:
	- Subdomain - status
	- Domain - paduch.xyz
	- Path - puste
	- Type - HTTP
	- URL - 10.0.0.201:3001
2. W konfiguracji Page Rule:
	- URL - status.paduch.xyz/
	- Pick a setting - Forwarding URL
	- Select status code - 301
	- Enter destinaion URL - https://status.paduch.xyz/status/homelab