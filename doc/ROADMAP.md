# Roadmap

High level.

## V2

Generate

- Using shared makefile
- Using go:generate

GRPC and CLI

- hooked up from sys up to Repo Man
- hooked up to sys-core fully
- v2 single and v3 dual binary

Sys-core: Cron
- Its needed for:
	- backups
	- sending reports from mod-disco
- Need ability for Cron to work off the DB
	- When changed, it makes sense to flush those in memory
	- Mhh seems we might need Subscribe off Badger DB earlier than i thought. Could use polling ( ironically a Cron) to just check the DB for changes.
- Need ability to access the schedules from the GRPC API.


Sys-core: Data

- Test data and real data
- embedded

sys-core: Migrate

- embedded
- available over CLI
- expressed read only in Flutter.

Sys-core: Ops

- API working for install, backup, restore
	- go tests doing it.
- Config

Sys-acconts

- Flutter Dialoge based SignUp, SignIn, Change apssword, Recover word
	- needs email
	- needs email templates.
mod-accont
	- using sys accont


## V3

sys
- subscribe to badger updates
	- this will make alot of things easier.
	- there is an option to use NATS also but only if we embed it.
		- In which case the event from subscribe will be sent to NATS.

mod-ion
- working of badger, and not redis.
