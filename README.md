# authsentry

Detector de brute-force e varredura em logs de autenticação.

## O que faz

Esta ferramenta de **defensiva** contra alvos que voce possui ou tem autorizacao. Detector de brute-force e varredura em logs de autenticação. O codigo e
testavel localmente (sem dependencias de rede para os testes unitarios).

> **Aviso etico:** uso exclusivo para fins educacionais e testes em ambientes
> que voce **possui** ou tem **autorizacao expressa** para auditar. Nunca a
> utilize contra sistemas de terceiros. O autor nao se responsabiliza por uso
> indevido.

## Instalacao

```bash
git clone https://github.com/Diogo-Damasceno/authsentry.git
cd authsentry
python3 -m venv .venv && . .venv/bin/activate
pip install -e .
```

## Uso

Aponte para seus próprios logs para medir tentativas de intrusão.

## Exemplos reais

```bash
$ auth-log-watch /var/log/auth.log
# ssh-brute: 142
```
```bash
$ echo 'Failed password for root' | auth-log-watch
# ssh-brute: 1
```

## Como funciona (resumo)

O modulo principal implementa a logica em funcoes puras e testaveis; a CLI e
apenas a casca de argumentos. Os testes em `tests/` (Python) ou `CoreTest.java`
(Java) cobrem os casos principais e rodam offline.

## O que NAO faz

- Nao executa ataques contra terceiros.
- Nao exfiltra dados.
- Nao substitui uma solucao comercial de seguranca.

## Licenca

MIT — ver `LICENSE`.
