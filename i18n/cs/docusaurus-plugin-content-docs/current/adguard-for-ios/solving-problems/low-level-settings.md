---
title: Průvodce nízkoúrovňových nastavení
sidebar_position: 5
---

:::info

Tento článek popisuje AdGuard pro iOS, multifunkční blokátor reklam, který chrání vaše zařízení na úrovni systému. Chcete-li zjistit, jak funguje, [stáhněte si aplikaci AdGuard](https://agrd.io/download-kb-adblock)

:::

## Jak dosáhnout nízkoúrovňových nastavení

:::caution

Změna *Nízkoúrovňových nastavení* může způsobit problémy s výkonem AdGuardu, může přerušit internetové připojení nebo ohrozit vaši bezpečnost a soukromí. Tuto část byste měli otevřít pouze v případě, že jste si jisti tím, co děláte, nebo pokud se vás na to zeptal náš tým podpory.

:::

Chcete-li přejít na *Nízkoúrovňová nastavení*, klepněte na ikonu ozubeného kola v pravém dolním rohu obrazovky a otevřete *Nastavení*. Vyberte sekci *Obecné* a poté přepněte přepínač *Pokročilý režim*, poté se níže zobrazí sekce *Pokročilá nastavení*. Klepnutím na *Pokročilá nastavení* přejděte do části *Nízkoúrovňová nastavení*.

## Nízkoúrovňová nastavení

### Režim Tunel

Existují dva hlavní režimy tunelu: *Dělený* a *Úplný*. Režim *Dělený tunel* poskytuje kompatibilitu aplikací AdGuard a takzvaných "Osobních VPN". V režimu *Úplný tunel* nemůže žádná jiná VPN pracovat současně s AdGuardem.

Existuje specifická funkce režimu *Dělený tunel*: pokud proxy server DNS nefunguje dobře, například pokud se odpověď ze serveru AdGuard DNS nevrátila včas, systém iOS jej "zneplatní" a přesměruje provoz přes server DNS zadaný v nastavení systému iOS. V tuto chvíli nejsou blokovány žádné reklamy a provoz DNS není šifrován.

V režimu *Úplný tunel* se používá pouze server DNS zadaný v nastavení AdGuardu. Pokud neodpovídá, internet jednoduše nefunguje. Zapnutý režim *Úplný tunel* může způsobit nesprávný výkon některých programů (například FaceTime) a vést k problémům s aktualizacemi aplikací.

Ve výchozím nastavení používá AdGuard režim *Dělený tunel* jako nejstabilnější možnost.

K dispozici je také další režim nazvaný *Úplný tunel (bez ikony VPN)*. Tento režim je naprosto stejný jako režim *Úplný tunel*, ale je nastaven tak, že se v systémovém řádku nezobrazuje ikona VPN.

### Režim blokování

In this module you can select the way AdGuard will respond to DNS queries that should be blocked:

- Default — respond with zero IP address when blocked by adblock-style rules; respond with the IP address specified in the rule when blocked by /etc/hosts-style rules
- REFUSED — respond with REFUSED code
- NXDOMAIN — respond with NXDOMAIN code
- Unspecified IP — respond with zero IP address
- Custom IP — respond with a manually set IP address

### Blokování IPv6

By moving the toggle to the right, you activate the blocking of IPv6 queries (AAAA requests). AAAA-type DNS requests will not be resolved, hence only IPv4 queries can be processed.

### Blokovaná odezva TTL

Here you can set the period for a device to cache the response to a DNS request. During the specified time to live (in seconds) the request can be read from the cache without re-requesting the DNS server.

### Bootstrap servery

Pro DNS-over-HTTPS, DNS-over-TLS a DNS-over-QUIC je vyžadován bootstrap server pro získání IP adresy hlavního serveru DNS. Pokud není zadán, použije se jako bootstrap server DNS server z nastavení systému iOS.

### Záložní server

Zde můžete zadat alternativní server, na který bude požadavek přesměrován, pokud hlavní server neodpoví. Pokud není zadán, použije se jako záložní server systémový DNS server. Je také možné zadat `žádný`, v tomto případě nebude nastaven žádný záložní server a bude použit pouze hlavní DNS server.

### Doba obnovení aplikace na pozadí

Zde můžete vybrat frekvenci, s jakou bude aplikace na pozadí kontrolovat aktualizace filtrů. Všimněte si, že kontroly aktualizací nebudou prováděny častěji než v zadané periodě, ale přesné intervaly nemusí být dodrženy.
