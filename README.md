<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(f"# {config['name'].title()}")
]]]-->
# Felons
<!--//[[[end]]]-->

## Mission

Tilt's mission is to map every theme to a basket of stocks for anyone to invest in. Mappings are AI generated and expert curated.
Expert improvements are accepted if they provide a better representation of a given theme.

## Theme Prompt
<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(config['prompt'])
]]]-->
Companies that are run by felons are willing to take more risks. The world is packed with regulations that need to be broken, those run by felons can bend the law to earn more. Trump has opened the door showing even felons can run for president.
<!--[[[end]]]-->

## Theme Stocks

<!--[[[cog
import cog
import csv
import json

with open('context.json') as file:
  contexts = json.load(file)

def _get_context_str_for_ticker(ticker):
  try:
    context = contexts[ticker]
    context_str = context['chat_gpt'] or context['claude'] or ""
  except KeyError:
    context_str = ""

  return context_str

cog.outl("| Ticker  | Context | Source |")
cog.outl("| ------- | ---- | ---- |")

with open('theme.csv') as file:
  reader = csv.reader(file)
  next(reader) # skip the header
  for row in reader:
    context_str = _get_context_str_for_ticker(row[0])
    cog.outl(f"| {row[0]} | {context_str} | {row[1]} |")
]]]-->
| Ticker  | Context | Source |
| ------- | ---- | ---- |
| GS | Goldman Sachs has faced legal issues related to financial practices but remains a leading investment bank. | chat_gpt |
| PFE | Pfizer has faced legal challenges over drug pricing and marketing practices but remains a leading pharmaceutical company. | chat_gpt |
| PLTR | Palantir, co-founded by Peter Thiel, has faced scrutiny over its data practices but continues to secure government contracts. | chat_gpt |
| UBER | Uber has a history of regulatory battles and aggressive market tactics, yet remains a dominant player in ride-sharing. | chat_gpt |
| WFC | Wells Fargo has been involved in multiple scandals but continues to be a major player in the banking industry. | chat_gpt |
| AMC |  | twitter |
| DJT |  | twitter |
| FNGR |  | twitter |
| GME |  | twitter |
| SCLX |  | twitter |
| CXW | CoreCivic, a private prison company, may benefit from relaxed regulations and a willingness to cut corners to maximize profits. | claude |
| GEO | The GEO Group, another private prison operator, could see increased business as felon-run companies seek cost-cutting measures. | claude |
| MPC | Marathon Petroleum, another refining company, may be more aggressive in expanding operations and lobbying for favorable policies. | claude |
| TRGP | Targa Resources, an energy infrastructure company, may be more likely to skirt environmental regulations under felon leadership. | claude |
| VLO | Valero Energy, a petroleum refining company, could benefit from leaders willing to push the boundaries of safety and environmental standards. | claude |
| TKO |  | manual |
<!--[[[end]]]-->

## License

<p>
This project is licensed under <a href="./LICENSE">AGPLv3</a>.
</p>


## Contributors

Thank you for your improvements! We appreciate all the contributions from the community.

<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  repo = config['github_repo'].lower()
  cog.outl(f'<a href="https://github.com/gettilt/{repo}/graphs/contributors">')
  cog.outl(f'  <img src="https://contrib.rocks/image?repo=gettilt/{repo}" />')
  cog.outl('</a>')
]]]-->
<a href="https://github.com/gettilt/felons/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=gettilt/felons" />
</a>
<!--[[[end]]]-->

## Join Our Community

<a href="https://discord.gg/4vYMhRpaMY" target="_blank">
<img src="https://discord.com/api/guilds/1179775688421683220/widget.png?style=banner3" alt="">
</a>
