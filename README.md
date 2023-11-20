Все, ради одного поля - NetWorth

Go-OpenDota is a simple Go package for accessing the [OpenDota API](https://docs.opendota.com/#).  

Successful queries return native Go structs.

### Services

* Benchmarks
* Distributions
* Explorer
* Health
* Hero Stats
* Heroes
* Leagues
* Live
* Matches
* Metadata
* Players
* Pro Matches
* Pro Players
* Public Matches
* Rankings 
* Records 
* Replays
* Schema
* Search
* Status
* Teams 

## Install

```bash
go get github.com/freemy/go-opendota
```

## Examples

### Match

```go
// OpenDota client
client := opendota.NewClient(httpClient)

// Get Match Data
match, res, err := client.MatchService.Match(3559037317)
fmt.Println(match.DireTeam.Name, "VS", match.RadiantTeam.Name)
```

### Player

```go
// OpenDota client
client := opendota.NewClient(httpClient)

// Get Player Data
player, res, err := client.PlayerService.Player(111620041)
fmt.Println(player.Profile.Name, player.SoloCompetitiveRank)

// Player Param
params := &opendota.PlayerParam{
	Win: 1,
}
// Get Won Matches For Player
wins, res, err := client.PlayerService.Matches(111620041, params)
for _, game := range wins {
	fmt.Println(game.MatchID, game.HeroID)
}
```

## License

[MIT License](LICENSE)

## Gopher 

Thanks to [Maria Ninfa](http://marianinfa.mx/) for the Gopher!
