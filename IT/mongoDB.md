# Mongo Config on Windows

These commands are for Windows user

- [Documentation](https://docs.mongodb.com/manual/reference/configuration-options/)

If you want to change the moogoDB config, for example, the `bindIp`

## Stop the daemon

```powershell
net stop mongodb
```

> Legend :
>
> - You need to run it as admin

## Change your config

You change the config here, located in `<install directory>\bin\mongod.cfg`

Remember it's a YAML file, so you need to produce a correct file

> no tabs but spaces !

You need to have admin rights to change the config file

## Start the mongoDB daemon

```powershell
net start mongodb
```

> Legend :
>
> - You need to run it as admin
