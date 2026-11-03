# 0001. Izbira tehnološkega sklada

- **Status:** proposed
- **Date:** 2026-11-03
- **Deciders:** Matic Kontelj

## Context

Za razvoj aplikacije Recipe Box potrebujemo tehnologije za izdelavo zalednega dela, spletnega uporabniškega vmesnika in shranjevanje podatkov.

Želimo izbrati tehnologije, ki omogočajo enostaven razvoj, dobro dokumentacijo, testiranje in možnost nadaljnje nadgradnje aplikacije.

Pri izbiri upoštevamo tudi predznanje programskega jezika Java in Python.

## Options considered

1. **Java + Spring Boot, React + TypeScript, PostgreSQL**
   - Prednosti: uporaba znanega programskega jezika Java, dobra podpora za REST API, veliko dokumentacije, zanesljiva relacijska podatkovna baza.
   - Slabosti: potrebno se je naučiti ogrodja Spring Boot in knjižnice React.

2. **Python + FastAPI, React + TypeScript, PostgreSQL**
   - Prednosti: Python je enostaven za uporabo, FastAPI omogoča hitro izdelavo REST API-ja.
   - Slabosti: zahteva uporabo drugega programskega jezika za backend.

3. **Node.js + Express, React + TypeScript, MySQL**
   - Prednosti: JavaScript oziroma TypeScript je mogoče uporabljati tako na backendu kot frontend delu.
   - Slabosti: potrebno je osvojiti dodatno okolje za razvoj backend dela.

## Decision

Izbrali smo **Java + Spring Boot** za backend, **React + TypeScript** za frontend in **PostgreSQL** za podatkovno bazo.

Odločitev temelji na predznanju Jave, dobri podpori za razvoj spletnih API-jev ter zanesljivosti in razširljivosti izbranih tehnologij.

## Consequences

- Pri razvoju backend dela bomo uporabljali Javo in Spring Boot.
- Za spletni uporabniški vmesnik bomo uporabljali React in TypeScript.
- Podatke bomo shranjevali v PostgreSQL.
- Naučiti se bomo morali uporabe Spring Boot in React.
- Tehnologije omogočajo nadaljnje testiranje, vzdrževanje in nadgradnjo aplikacije.