##### Installation

```sh
pip install https://github.com/Vivekkumar-IN/TheApi/archive/refs/heads/main.zip
```

---

# 📘 API Documentation

Welcome to the **TheApi**! This library allows you to easily interact with the API using both **synchronous** and **asynchronous** options.

- **Sync**: `from TheApi.sync import api`
- **Async**: `from TheApi import api`

Below, we’ll cover each function, providing examples and expected results so you can get started quickly! Let’s dive in 🚀

## Status

| Function           | Status |
|--------------------|--------|
| [1. Animechan](#1-animechan) | ✅
| [2. Bing Image](#2-bing-image) | ✅
| [3. Blackpink](#3-blackpink) | ✅
| [4. Carbon](#4-carbon) | ✅
| [5. Cat](#5-cat) | ✅
| [6. Dog](#6-dog) | ✅
| [7. Domain Search](#7-domain-search) | ✅
| [8. Fox](#8-fox) | ✅
| [9. Get Advice](#9-get-advice) | ✅
| [10. Get Hindi Jokes](#10-get-hindi-jokes) | ✅
| [11. Get Jokes](#11-get-jokes) | ✅
| [12. Get Uselessfact](#12-get-uselessfact) | ✅
| [13. Github Search](#13-github-search) | ✅
| [14. Hindi Quote](#14-hindi-quote) | ✅
| [15. Hug](#15-hug) | ✅
| [16. Meme](#16-meme) | ✅
| [17. Neko](#17-neko) | ✅
| [18. Pypi](#18-pypi) | ✅
| [19. Quote](#19-quote) | ✅
| [20. Random Word](#20-random-word) | ✅
| [21. Riddle](#21-riddle) | ✅
| [22. Stackoverflow Search](#22-stackoverflow-search) | ✅
| [23. Upload Image](#23-upload-image) | ✅
| [24. Wikipedia](#24-wikipedia) | ✅
| [25. Words](#25-words) | ✅
| [26. Write](#26-write) | ✅


## 🎓 How to Use Each Function

### 1. Animechan

**Description**:
Fetches a random anime quote from the AnimeChan API.

**Returns:**
  - **dict**: Contains the quote content, anime name, and character details.

```python
from TheApi import api

result = await api.animechan()
print(result)
```

#### Expected Output

```json
{
    "content": "I placed this blade of grass in my mouth thinking I'd look cool. But it must be poison 'cause ith makinth ma mouth numb.",
    "anime": {
        "id": 222,
        "name": "Bleach"
    },
    "character": {
        "id": 2489,
        "name": "Shunsui Ky\u014draku"
    }
}
```

### 2. Bing Image

**Description**:
Searches Bing for images based on a query and retrieves image URLs.

**Args:**
  - **query (str)**: The search query string for finding images.
  - **limit (int, optional)**: The maximum number of image URLs to return. Defaults to 3.

**Returns:**
  - **list**: A list of image URLs retrieved from the Bing search results.

```python
from TheApi import api

result = await api.bing_image(query='Pokemon', limit=3)
print(result)
```

#### Expected Output

```text
https://media.gamestop.com/i/gamestop/11103360/New-Pokemon-Snap---Nintendo-Switch
https://assets-prd.ignimgs.com/2021/03/01/new-pokemon-snap-button-1614639848584.jpg
https://img-eshop.cdn.nintendo.net/i/00bd7efe46ab2b3ff0774172a5d4f21a5b2f467b3e324557ce1e9a9ae12c1d3b.jpg
https://www.nme.com/wp-content/uploads/2021/05/New-Pokemon-Snap-Credit-Bandai-Namco-HERO@2000x1270.jpg
https://www.rpgfan.com/wp-content/uploads/2021/01/New-Pokemon-Snap-Screenshot-044.jpg
https://www.gamespot.com/a/uploads/screen_kubrick/123/1239113/3801204-6238037227-screenshot02.jpg
https://www.videogamer.com/wp-content/uploads/01d7162d-749b-43eb-bdcc-5c0cf9e49881_New_Pokmon_Snap_Main.jpg
https://cdn.vox-cdn.com/thumbor/Lgiz7lrS_auxnKixNMsWmsx_ETE=/1400x788/filters:format(jpeg)/cdn.vox-cdn.com/uploads/chorus_asset/file/22473880/Switch_NewPokemonSnap_Screenshots_Feb26__9_.jpg
https://media.npr.org/assets/img/2021/04/29/snap-1_wide-7c41973fe9eef7cbc49beec9a59f3bf5410187d2-s1400-c100.jpg
https://images.launchbox-app.com/fc92b8c7-704f-43e9-ab5a-407b712bc662.jpg
https://assets.gamepur.com/wp-content/uploads/2021/01/14074110/new-pokemon-snap-arrives-on-nintendo-switch-this-april.jpg
https://assets.nintendo.com/image/upload/c_fill,w_1200/q_auto:best/f_auto/dpr_2.0/ncom/en_US/products/games/switch/new-pokemon-snap/110735-switch-new-pokemon-snap-us-1200x675
https://cdn.mobilesyrup.com/wp-content/uploads/2021/01/new-pokemon-snap-screenshot-2.jpg
https://images.launchbox-app.com/1f06f096-8eb6-43ac-abbb-262deb1bf596.jpg
https://upload.wikimedia.org/wikipedia/en/thumb/8/84/POKEMON_SNAP_GAMEPLAY.jpg/220px-POKEMON_SNAP_GAMEPLAY.jpg
https://static1.colliderimages.com/wordpress/wp-content/uploads/2021/04/pokemon-snap.png
https://videogamesuncovered.com/wp-content/uploads/2021/01/new-pokemon-snap-social.jpg
https://i0.wp.com/mynintendonews.com/wp-content/uploads/2021/01/new_pokemon_snap_logo.jpg?ssl=1
https://i.gadgets360cdn.com/products/large/New-Pokemon-Snap-Wallpaper-1440x2560-1000x1778-1646977124.jpg
https://www.nintendo.com/sg/switch/arft/img/hero_sp.jpg
https://upload.wikimedia.org/wikipedia/commons/thumb/9/97/Pokemon_Type_Chart.svg/2048px-Pokemon_Type_Chart.svg.png
https://vignette.wikia.nocookie.net/pokemon/images/8/8c/PokemonTypes.png/revision/latest?cb=20170417193722
https://videogamesuncovered.com/wp-content/uploads/2016/12/pokemon-types.jpg
https://www.theloadout.com/wp-content/sites/theloadout/2023/06/pokemon-type-chart-icons.jpg
https://i.pinimg.com/originals/c4/c7/79/c4c779a2c89ebcc0d1fa61a21e03640d.png
https://res.cloudinary.com/lmn/image/upload/e_sharpen:150,f_auto,fl_lossy,q_80/v1/gameskinnyc/p/o/k/pokemon-types-table-ad163.png
https://cdn1.vectorstock.com/i/1000x1000/03/95/pokemon-type-symbols-vector-2700395.jpg
https://external-preview.redd.it/GhUNDBJN4b3NpRRIenzN9nEWV4tsuC9KI4lvj_VfbWA.png?auto=webp&amp;s=f4b4a9cf1726f3c4b785044116a245e6787877b7
https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/dc175766-6e5d-4e29-a6c5-ecc6a37db16a/d8vkfwp-b481a558-5c32-44b6-b4d0-df9f1e8ed8f1.png/v1/fill/w_1600,h_1340,q_80,strp/illustrated_pokemon_type_chart_by_jojostory_d8vkfwp-fullview.jpg?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7ImhlaWdodCI6Ijw9MTM0MCIsInBhdGgiOiJcL2ZcL2RjMTc1NzY2LTZlNWQtNGUyOS1hNmM1LWVjYzZhMzdkYjE2YVwvZDh2a2Z3cC1iNDgxYTU1OC01YzMyLTQ0YjYtYjRkMC1kZjlmMWU4ZWQ4ZjEucG5nIiwid2lkdGgiOiI8PTE2MDAifV1dLCJhdWQiOlsidXJuOnNlcnZpY2U6aW1hZ2Uub3BlcmF0aW9ucyJdfQ.7rruD0XfA3p4nDeOv404ZBC2Wl_QB2hCOO0xsTdi1R0
https://www.mandatory.gg/wp-content/uploads/mandatory-guide-pokemon-ecarlate-violet-table-types-forces-faiblesses.png
https://3.bp.blogspot.com/-b8i_WR7eoI0/WV8bxYVOZBI/AAAAAAAAGck/5nEIhuF-zMASQfxBF6JhSw6SRfjVh7ocACKgBGAs/s1600/ENG-05-02-02-Pokemon-type-chart.png
https://i.pinimg.com/originals/95/b2/6f/95b26f7cd39e206259faa20fd57e7b47.png
https://raw.githubusercontent.com/kennycason/cellular-automata-pokemon-types/master/data/pokemon_gen1_type_chart.png?raw=true
https://i.ytimg.com/vi/H1w2VoRqmQQ/maxresdefault.jpg
https://releasegaming.com/wp-content/uploads/2023/02/Pokemon-Type-Chart-Poster-960x850.jpg
http://images6.fanpop.com/image/photos/34100000/Pokemon-types-pokemon-34164928-846-1824.jpg
https://1.bp.blogspot.com/-A0NsVJu2Ay0/WGOgGNxAdTI/AAAAAAAABIY/amMTic8SsXYs7jfP_ITwBmkeVQHIAGZ-ACPcB/s1600/ENG-05-02-02-All-the-Pokemon-types.png
http://img.pokemondb.net/images/typechart.png
http://fc09.deviantart.net/fs70/i/2013/318/0/f/pokemon_types_wheel_by_kamionero-d6u6o9i.png
https://vignette3.wikia.nocookie.net/pokemonadventure/images/a/ad/Symbols.png/revision/latest?cb=20121003192408
https://cdn11.bigcommerce.com/s-0kvv9/images/stencil/2560w/products/175831/251398/pokemonshininglegends28__52193.1509648391.jpg?c=2
https://images.saymedia-content.com/.image/t_share/MTc5ODE2MjE2Mjc2NDQ0Nzgz/best-v-pokemon-cards.jpg
https://www.pokemoncenter.com/products/images/P2373PC/155-80156/P2373PC_155-80156_01.jpg
https://i.pinimg.com/736x/83/e3/5a/83e35aead31fabb77b9bde3396d4351f.jpg
https://i.pinimg.com/originals/18/28/97/18289747d16a23e3dc20cc36956b9b4b.jpg
https://imgix.ranker.com/user_node_img/3181/63618188/original/blastoise-u16?fit=crop&amp;fm=pjpg&amp;q=60&amp;w=650&amp;dpr=2
https://m.media-amazon.com/images/I/91lXJ99OooL.jpg
https://www.totsafe.com/wp-content/uploads/2020/09/Gyarados-Ancient-Origins-Holo-1446x2048.jpg
https://m.media-amazon.com/images/I/71p-47sRv9L.jpg
https://mlpnk72yciwc.i.optimole.com/cqhiHLc.WqA8~2eefa/w:auto/h:auto/q:75/https://bleedingcool.com/wp-content/uploads/2020/06/Charizard-grade-9-mint-front.jpg
https://www.oldsportscards.com/wp-content/uploads/2019/12/Most-Valuable-First-Edition-Pokemon-Cards.jpg
https://i.etsystatic.com/26687506/r/il/01dacc/2853951539/il_1588xN.2853951539_obpw.jpg
https://i.etsystatic.com/22464198/r/il/92a686/2662042144/il_1140xN.2662042144_ns4d.jpg
https://i.etsystatic.com/24353291/r/il/358485/2689751041/il_fullxfull.2689751041_ofmo.jpg
https://i.etsystatic.com/22089514/r/il/ecff88/4140836231/il_1080xN.4140836231_cpmu.jpg
https://i.redd.it/jtyx6uktb8r21.jpg
https://images.saymedia-content.com/.image/t_share/MTgzNzE1NDA2MDk0MDE3ODU1/best-vmax-pokemon-cards.png
https://i.etsystatic.com/22089514/r/il/c4b57e/2338029595/il_1140xN.2338029595_sei2.jpg
https://pm1.narvii.com/6267/3e8dabe202aa4911724963a0eb1b1f0b0c875193_hq.jpg
https://i.etsystatic.com/22089514/r/il/c9fa64/4093173358/il_1140xN.4093173358_jv87.jpg
https://static3.cbrimages.com/wordpress/wp-content/uploads/2019/09/Pokemon-Ash-Feature-Image-1.jpg
https://townsquare.media/site/622/files/2016/08/poke-feat.jpg?w=1200&amp;h=0&amp;zc=1&amp;s=0&amp;a=t&amp;q=89
http://www.animextremist.com/imagenes/pokemon/pokemon103.jpg
```

### 3. Blackpink

**Description**:
Creates a stylized "Blackpink"-themed image with custom text, color, and optional border.

**Args:**
  - **query (str)**: The text to display on the image.
  - **color (str, optional)**: The primary color of the text and gradient background in hex format.
    Defaults to "#ff94e0" (a pink shade).
  - **border_color (str, optional)**: The color of the image border in hex format.
    If not provided, defaults to the value of `color`.

**Returns:**
  - **FilePath**: The file path of the generated image with delete attribute.

```python
from TheApi import api

result = await api.blackpink(query='Pokemon', color='#ff94e0', border_color=None)
print(result)
```

#### Expected Output

```text
/home/runner/work/TheApi/TheApi/downloads/blackpink_jJsoJBVh.jpg
```

### 4. Carbon

**Description**:
Generates a code snippet image using the Carbon API, saves it to the downloads folder, uploads it, and returns the URL of the uploaded image.

**Args:**
  - **query (str)**: The code snippet to be rendered as an image.

**Returns:**
  - **FilePath**: The file path of the saved image.

```python
from TheApi import api

result = await api.carbon(query='Pokemon')
print(result)
```

#### Expected Output

```text
/home/runner/work/TheApi/TheApi/downloads/carbon_eGIiJdUJ.png
```

### 5. Cat

**Description**:
Fetches a random cat image URL.

**Returns:**
  - **str or None**: The URL of a random cat image if available; None if no response is received.

```python
from TheApi import api

result = await api.cat()
print(result)
```

#### Expected Output

```text
https://cdn2.thecatapi.com/images/MTY3NTkxNw.jpg
```

### 6. Dog

**Description**:
Fetches a random dog image URL.

**Returns:**
  - **str or None**: The URL of a random dog image if available; None if no response is received.

```python
from TheApi import api

result = await api.dog()
print(result)
```

#### Expected Output

```text
https://random.dog/28f07efd-c0a8-482a-b1f6-5823256f7a71.mp4
```

### 7. Domain Search

**Description**:
Fetches domain information from the DomainsDB API.

**Args:**
  - **domain (str)**: The domain name to search for (e.g., "facebook").
  - **zone (str)**: The domain zone to search within (e.g., "com").Default is "com".

**Returns:**
  - **dict**: A dictionary containing the results of the domain search.

```python
from TheApi import api

result = await api.domain_search(domain='Pokemon', zone='com')
print(result)
```

#### Expected Output

```json
{
    "domains": [
        {
            "domain": "pokemon-pcg-pocket.com",
            "create_date": "2024-11-13T12:59:34.788589",
            "update_date": "2024-11-13T12:59:34.788591",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "the-pokemon-store.com",
            "create_date": "2024-11-10T12:00:23.641438",
            "update_date": "2024-11-10T12:00:23.641441",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-tcgp.com",
            "create_date": "2024-11-07T08:41:00.387999",
            "update_date": "2024-11-07T08:41:00.388001",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-collect.com",
            "create_date": "2024-11-07T08:41:00.387827",
            "update_date": "2024-11-07T08:41:00.387830",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-glazed.com",
            "create_date": "2024-11-04T00:30:39.204506",
            "update_date": "2024-11-04T00:30:39.204508",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-energy.com",
            "create_date": "2024-11-04T00:30:39.204309",
            "update_date": "2024-11-04T00:30:39.204312",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-italy.com",
            "create_date": "2024-11-04T00:30:39.204707",
            "update_date": "2024-11-04T00:30:39.204709",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-autochess.com",
            "create_date": "2024-11-02T08:33:16.991832",
            "update_date": "2024-11-02T08:33:16.991834",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "play-pokemon-online.com",
            "create_date": "2024-11-02T08:33:16.825655",
            "update_date": "2024-11-02T08:33:16.825658",
            "country": "US",
            "isDead": "False",
            "A": [
                "104.148.94.51"
            ],
            "NS": [
                "jm1.dns.com",
                "jm2.dns.com"
            ],
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "japanese-pokemon-cards.com",
            "create_date": "2024-11-02T08:33:00.325331",
            "update_date": "2024-11-02T08:33:00.325336",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-peluches.com",
            "create_date": "2024-10-24T04:12:03.540008",
            "update_date": "2024-10-24T04:12:03.540011",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-dynasty.com",
            "create_date": "2024-10-18T03:14:43.852622",
            "update_date": "2024-10-18T03:14:43.852624",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-quiz.com",
            "create_date": "2024-10-15T03:36:57.588519",
            "update_date": "2024-10-15T03:36:57.588522",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-tcg-pocket-dex.com",
            "create_date": "2024-10-07T13:29:47.356011",
            "update_date": "2024-10-07T13:29:47.356013",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-mystery-boxes.com",
            "create_date": "2024-10-07T13:29:47.355854",
            "update_date": "2024-10-07T13:29:47.355856",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-oise.com",
            "create_date": "2024-10-06T00:23:47.700295",
            "update_date": "2024-10-06T00:23:47.700297",
            "country": "BE",
            "isDead": "False",
            "A": [
                "62.213.245.149"
            ],
            "NS": [
                "ns3.ipower.be",
                "ns2.ipower.be",
                "ns1.ipower.be"
            ],
            "CNAME": null,
            "MX": [
                {
                    "exchange": "mail.pokemon-oise.com",
                    "priority": 10
                }
            ],
            "TXT": null
        },
        {
            "domain": "pokemon-pocketdex.com",
            "create_date": "2024-10-03T10:22:44.808048",
            "update_date": "2024-10-03T10:22:44.808050",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-aventure.com",
            "create_date": "2024-09-30T10:50:27.835203",
            "update_date": "2024-09-30T10:50:27.835206",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-news.com",
            "create_date": "2024-09-24T09:20:31.631508",
            "update_date": "2024-09-24T09:20:31.631511",
            "country": "US",
            "isDead": "False",
            "A": [
                "198.54.114.204"
            ],
            "NS": [
                "dns1.namecheaphosting.com",
                "dns2.namecheaphosting.com"
            ],
            "CNAME": null,
            "MX": [
                {
                    "exchange": "mail.pokemon-news.com",
                    "priority": 0
                }
            ],
            "TXT": null
        },
        {
            "domain": "pokemon-pcmaster.com",
            "create_date": "2024-09-24T09:20:31.631693",
            "update_date": "2024-09-24T09:20:31.631695",
            "country": "US",
            "isDead": "False",
            "A": [
                "154.221.215.205"
            ],
            "NS": [
                "now1.dns.com",
                "now2.dns.com"
            ],
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-pokedex.com",
            "create_date": "2024-09-21T21:40:29.481566",
            "update_date": "2024-09-21T21:40:29.481568",
            "country": "US",
            "isDead": "False",
            "A": [
                "207.244.67.214"
            ],
            "NS": [
                "ns1.dnsnuts.com",
                "ns2.dnsnuts.com"
            ],
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-gba.com",
            "create_date": "2024-09-18T23:10:09.788582",
            "update_date": "2024-09-18T23:10:09.788584",
            "country": "JP",
            "isDead": "False",
            "A": [
                "219.94.203.121"
            ],
            "NS": [
                "ns5.xserver.jp",
                "ns3.xserver.jp",
                "ns1.xserver.jp",
                "ns4.xserver.jp",
                "ns2.xserver.jp"
            ],
            "CNAME": null,
            "MX": [
                {
                    "exchange": "pokemon-gba.com",
                    "priority": 0
                }
            ],
            "TXT": null
        },
        {
            "domain": "pokemon-dp.com",
            "create_date": "2024-09-18T23:10:09.788393",
            "update_date": "2024-09-18T23:10:09.788395",
            "country": "JP",
            "isDead": "False",
            "A": [
                "211.5.69.234"
            ],
            "NS": [
                "ns1.c008jp5381.info",
                "ns2.c008jp5381.info"
            ],
            "CNAME": null,
            "MX": [
                {
                    "exchange": "pokemon-dp.com",
                    "priority": 0
                }
            ],
            "TXT": null
        },
        {
            "domain": "pokemon-underground.com",
            "create_date": "2024-09-18T23:10:09.788937",
            "update_date": "2024-09-18T23:10:09.788939",
            "country": "JP",
            "isDead": "False",
            "A": [
                "61.198.74.245"
            ],
            "NS": [
                "ns1.value-domain.com",
                "ns2.value-domain.com"
            ],
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-aona.com",
            "create_date": "2024-09-18T23:10:09.788186",
            "update_date": "2024-09-18T23:10:09.788190",
            "country": "US",
            "isDead": "False",
            "A": [
                "13.249.39.146",
                "13.249.39.52",
                "13.249.39.37",
                "13.249.39.224"
            ],
            "NS": [
                "ns-1376.awsdns-44.org",
                "ns-1782.awsdns-30.co.uk",
                "ns-394.awsdns-49.com",
                "ns-599.awsdns-10.net"
            ],
            "CNAME": null,
            "MX": [
                {
                    "exchange": "mx.pokemon-aona.com.cust.hostedemail.com",
                    "priority": 10
                }
            ],
            "TXT": null
        },
        {
            "domain": "pokemon-legends.com",
            "create_date": "2024-09-08T09:54:29.699715",
            "update_date": "2024-09-08T09:54:29.699717",
            "country": "US",
            "isDead": "False",
            "A": [
                "3.33.152.147",
                "15.197.142.173"
            ],
            "NS": [
                "ns17.domaincontrol.com",
                "ns18.domaincontrol.com"
            ],
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-calculation-sv.com",
            "create_date": "2024-09-06T21:30:18.924253",
            "update_date": "2024-09-06T21:30:18.924256",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-dimension.com",
            "create_date": "2024-09-05T09:12:56.181647",
            "update_date": "2024-09-05T09:12:56.181650",
            "country": "FR",
            "isDead": "False",
            "A": [
                "87.98.174.30"
            ],
            "NS": [
                "dns1.e-c.com",
                "dns2.e-c.com"
            ],
            "CNAME": null,
            "MX": [
                {
                    "exchange": "pokemon-dimension.com",
                    "priority": 0
                }
            ],
            "TXT": [
                "v=spf1 ip4:87.98.174.30 +a +mx +ip4:87.98.153.102 ~all"
            ]
        },
        {
            "domain": "pokemon-go-home.com",
            "create_date": "2024-09-02T10:21:29.718289",
            "update_date": "2024-09-02T10:21:29.718291",
            "country": "US",
            "isDead": "False",
            "A": [
                "142.91.174.104"
            ],
            "NS": [
                "ns1.openprovider.nl",
                "ns2.openprovider.be",
                "ns3.openprovider.eu"
            ],
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-card-artwalk.com",
            "create_date": "2024-08-30T09:32:21.700506",
            "update_date": "2024-08-30T09:32:21.700509",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "eternara-pokemon-auto-chess.com",
            "create_date": "2024-08-30T09:31:51.471595",
            "update_date": "2024-08-30T09:31:51.471600",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-sea.com",
            "create_date": "2024-08-27T09:19:17.135535",
            "update_date": "2024-08-27T09:19:17.135538",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-master.com",
            "create_date": "2024-08-24T09:08:58.027448",
            "update_date": "2024-08-24T09:08:58.027450",
            "country": "JP",
            "isDead": "False",
            "A": [
                "150.95.8.162"
            ],
            "NS": [
                "01.dnsv.jp",
                "02.dnsv.jp",
                "03.dnsv.jp",
                "04.dnsv.jp"
            ],
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-rps.com",
            "create_date": "2024-08-24T09:08:58.027988",
            "update_date": "2024-08-24T09:08:58.027991",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-unite-matome.com",
            "create_date": "2024-08-22T21:11:38.525011",
            "update_date": "2024-08-22T21:11:38.525013",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-overdose.com",
            "create_date": "2024-08-21T09:47:14.599538",
            "update_date": "2024-08-21T09:47:14.599540",
            "country": "US",
            "isDead": "False",
            "A": [
                "104.18.49.225",
                "104.18.48.225"
            ],
            "NS": [
                "coco.ns.cloudflare.com",
                "sri.ns.cloudflare.com"
            ],
            "CNAME": null,
            "MX": [
                {
                    "exchange": "mail.pokemon-overdose.com",
                    "priority": 10
                }
            ],
            "TXT": null
        },
        {
            "domain": "pokemon-sprites-ethereum-blockchain-nfts-nintendo-collec.com",
            "create_date": "2024-08-05T17:00:04.645397",
            "update_date": "2024-08-05T17:00:04.645400",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-irl.com",
            "create_date": "2024-07-18T17:04:27.841240",
            "update_date": "2024-07-18T17:04:27.841243",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-event-kujisystem.com",
            "create_date": "2024-07-18T17:04:27.841055",
            "update_date": "2024-07-18T17:04:27.841057",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-display.com",
            "create_date": "2024-07-11T05:39:11.089164",
            "update_date": "2024-07-11T05:39:11.089166",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-cg-pocket22-blog.com",
            "create_date": "2024-07-08T14:33:48.093159",
            "update_date": "2024-07-08T14:33:48.093162",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-online-shop.com",
            "create_date": "2024-06-29T11:03:49.095970",
            "update_date": "2024-06-29T11:03:49.095972",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-gratuit.com",
            "create_date": "2024-06-29T11:03:49.095786",
            "update_date": "2024-06-29T11:03:49.095789",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-il.com",
            "create_date": "2024-06-23T14:23:12.231846",
            "update_date": "2024-06-23T14:23:12.231849",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-ro.com",
            "create_date": "2024-06-17T17:54:46.884838",
            "update_date": "2024-06-17T17:54:46.884840",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-pg.com",
            "create_date": "2024-06-16T06:26:10.992663",
            "update_date": "2024-06-16T06:26:10.992665",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-tcg-pocket.com",
            "create_date": "2024-06-05T23:00:55.523220",
            "update_date": "2024-06-05T23:00:55.523222",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-team-api.com",
            "create_date": "2024-06-04T12:18:16.410916",
            "update_date": "2024-06-04T12:18:16.410918",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-randomizer.com",
            "create_date": "2024-06-01T12:10:50.445501",
            "update_date": "2024-06-01T12:10:50.445504",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        },
        {
            "domain": "pokemon-manager.com",
            "create_date": "2024-05-19T09:55:57.912517",
            "update_date": "2024-05-19T09:55:57.912519",
            "country": null,
            "isDead": "False",
            "A": null,
            "NS": null,
            "CNAME": null,
            "MX": null,
            "TXT": null
        }
    ],
    "total": 354,
    "time": "8",
    "next_page": null
}
```

### 8. Fox

**Description**:
Fetches a random fox image URL.

**Returns:**
  - **str or None**: The URL of the fox image if available, otherwise None.

```python
from TheApi import api

result = await api.fox()
print(result)
```

#### Expected Output

```text
https://randomfox.ca/?i=47
```

### 9. Get Advice

**Description**:
Fetches a random piece of advice.

**Returns:**
  - **str**: A random advice message.

```python
from TheApi import api

result = await api.get_advice()
print(result)
```

#### Expected Output

```text
Everything matters, but nothing matters that much.
```

### 10. Get Hindi Jokes

**Description**:
Fetches a random Hindi joke.

**Returns:**
  - **str**: A random Hindi joke if available, or "No joke found" if not available.

```python
from TheApi import api

result = await api.get_hindi_jokes()
print(result)
```

#### Expected Output

```text
उम्र बढ़ती जा रही है और हरकतें सुधरने का नाम नहीं ले रही मेरी नहीं तुम सब लोगों की😆🤣😋😉 
```

### 11. Get Jokes

**Description**:
Fetches a specified number of jokes.

**Args:**
  - **amount (int, optional)**: The number of jokes to retrieve. Defaults to 1.

**Returns:**
  - **str**: A single joke if `amount` is 1. If `amount` > 1, returns numbered jokes as a formatted string.

```python
from TheApi import api

result = await api.get_jokes(amount=1)
print(result)
```

#### Expected Output

```text
What does the MacBook have in common with Donald Trump?

I would tell you....
But I don't compare apples to oranges.
```

### 12. Get Uselessfact

**Description**:
Fetches a random useless fact.

**Returns:**
  - **str**: A random useless fact.

```python
from TheApi import api

result = await api.get_uselessfact()
print(result)
```

#### Expected Output

```text
There are 293 ways to make change for a dollar.
```

### 13. Github Search

**Description**:
Searches GitHub for various types of content.

**Args:**
  - **query (str)**: The search query.
  - **search_type (str, optional)**: The type of search. Can be one of:
    - "repositories"
    - "users"
    - "organizations"
    - "issues"
    - "pull_requests"
    - "commits"
    - "topics"

**Description**:
Defaults to "repositories". max_results (int, optional): The maximum number of results to return. Defaults to 3.

**Returns:**
  - **list**: A list of search results or an error message.

```python
from TheApi import api

result = await api.github_search(query='Pokemon', search_type='repositories', max_results=3)
print(result)
```

#### Expected Output

```json
[
    {
        "name": "PokemonGo-Map",
        "full_name": "AHAAAAAAA/PokemonGo-Map",
        "description": "\ud83c\udf0f Live visualization of all the pokemon in your area... and more! (shutdown)",
        "url": "https://github.com/AHAAAAAAA/PokemonGo-Map",
        "language": null,
        "stargazers_count": 7529,
        "forks_count": 2815
    },
    {
        "name": "pokemon-showdown",
        "full_name": "smogon/pokemon-showdown",
        "description": "Pok\u00e9mon battle simulator.",
        "url": "https://github.com/smogon/pokemon-showdown",
        "language": "TypeScript",
        "stargazers_count": 4796,
        "forks_count": 2799
    },
    {
        "name": "PokemonGo-Bot",
        "full_name": "PokemonGoF/PokemonGo-Bot",
        "description": "The Pokemon Go Bot, baking with community.",
        "url": "https://github.com/PokemonGoF/PokemonGo-Bot",
        "language": "Python",
        "stargazers_count": 3871,
        "forks_count": 1543
    }
]
```

### 14. Hindi Quote

**Description**:
Fetches a random Hindi quote.

**Returns:**
  - **str**: The content of a random Hindi quote.

```python
from TheApi import api

result = await api.hindi_quote()
print(result)
```

#### Expected Output

```text
जीवन में ऊँचा उठने के लिए किसी डिग्री की जरुरत नहीं। अच्छे शब्द ही इंसान को बादशाह बना देते है।
```

### 15. Hug

**Description**:
Fetches a specified number hug gif from the Nekos.Best API.

**Args:**
  - **amount (int)**: The number of neko images to fetch. Defaults to 1.

**Returns:**
  - **list**: A list of dictionaries containing information about each fetched neko image or GIF.
    Each dictionary typically includes:
    - anime_name (str): The name of the anime.
    - url (str): The URL of the GIF.

```python
from TheApi import api

result = await api.hug(amount=1)
print(result)
```

#### Expected Output

```json
[
    {
        "anime_name": "Sword Art Online",
        "url": "https://nekos.best/api/v2/hug/548daa04-3dff-4524-bb28-c229e5542e9f.gif"
    }
]
```

### 16. Meme

**Description**:
Fetches a random meme image URL.

**Returns:**
  - **str or None**: The URL of the meme image if available, otherwise None.

```python
from TheApi import api

result = await api.meme()
print(result)
```

#### Expected Output

```text
https://preview.redd.it/79p7r99mot0e1.gif?width=640&crop=smart&format=png8&s=e9a44bc18f3f1c3e224d7ade898f7e495699839f
```

### 17. Neko

**Description**:
Fetches a specified number of neko images or GIFs from the Nekos.Best API.

**Args:**
  - **endpoint (str)**: The endpoint category to fetch content from. Default is "neko".
    Valid image endpoints:
    - "husbando", "kitsune", "neko", "waifu"
    Valid GIF endpoints:
    - "baka", "bite", "blush", "bored", "cry", "cuddle", "dance", "facepalm",
    "feed", "handhold", "handshake", "happy", "highfive", "hug", "kick",
    "kiss", "laugh", "lurk", "nod", "nom", "nope", "pat", "peck", "poke",
    "pout", "punch", "shoot", "shrug", "slap", "sleep", "smile", "smug",
    "stare", "think", "thumbsup", "tickle", "wave", "wink", "yawn", "yeet"
    amount (int): The number of items to fetch. Default is 3.

**Returns:**
  - **dict**: A dictionary containing the results of the request. The dictionary has a key `"results"`,
    which holds a list of items.

**Raises:**
  - **ValueError**: If the endpoint is not a valid category.

```python
from TheApi import api

result = await api.neko(endpoint='neko', amount=3)
print(result)
```

#### Expected Output

```json
{
    "results": [
        {
            "artist_href": "https://www.pixiv.net/en/users/34096559",
            "artist_name": "\u6749far-",
            "source_url": "https://www.pixiv.net/en/artworks/87660808",
            "url": "https://nekos.best/api/v2/neko/f66a2183-aaaf-4c30-b93f-304add2272f6.png"
        },
        {
            "artist_href": "https://www.pixiv.net/en/users/14089200",
            "artist_name": "\u62b9\u8336Amigo",
            "source_url": "https://www.pixiv.net/en/artworks/93733699",
            "url": "https://nekos.best/api/v2/neko/1b63d20d-1b51-4a93-840c-1ed00dccc442.png"
        },
        {
            "artist_href": "https://www.pixiv.net/en/users/10297869",
            "artist_name": "\u5c0f\u98af\u732b",
            "source_url": "https://www.pixiv.net/en/artworks/80280669",
            "url": "https://nekos.best/api/v2/neko/f44f42f1-44ce-4962-87a7-7f4552c6c3e3.png"
        }
    ]
}
```

### 18. Pypi

**Description**:
Retrieves metadata information about a specified Python package from the PyPI API.

**Args:**
  - **package_name (str)**: The name of the package to search for on PyPI.

**Returns:**
  - **dict or None**: A dictionary with relevant package information if found, containing:
    - name (str): Package name.
    - version (str): Latest package version.
    - summary (str): Short description of the package.
    - author (str): Package author.
    - author_email (str): Email of the package author.
    - license (str): License type.
    - home_page (str): URL of the package's homepage.
    - package_url (str): URL of the package on PyPI.
    - requires_python (str): Minimum Python version required.
    - keywords (str): Keywords associated with the package.
    - classifiers (list): List of PyPI classifiers.
    - project_urls (dict): Additional project URLs (e.g., source code, documentation).
    Returns None if the package is not found or there is an error.

```python
from TheApi import api

result = await api.pypi(package_name='Pokemon')
print(result)
```

#### Expected Output

```json
{
    "name": "pokemon",
    "version": "0.36",
    "summary": "ascii database of pokemon... in Python!",
    "author": "Vanessa Sochat",
    "author_email": "vsoch@noreply.github.users.com",
    "license": "LICENSE",
    "home_page": "https://github.com/vsoch/pokemon",
    "package_url": "https://pypi.org/project/pokemon/",
    "requires_python": "",
    "keywords": "pokemon,avatar,ascii,gravatar",
    "classifiers": [],
    "project_urls": {
        "Homepage": "https://github.com/vsoch/pokemon"
    }
}
```

### 19. Quote

**Description**:
Fetches a random quote.

**Returns:**
  - **str**: The content of a random quote followed by the author's name.

```python
from TheApi import api

result = await api.quote()
print(result)
```

#### Expected Output

```text
Never reach out your hand unless you're willing to extend an arm.

author - Pope Paul VI
```

### 20. Random Word

**Description**:
Fetches a random word.

**Returns:**
  - **str**: A random word if available; "None" if an error occurs.

```python
from TheApi import api

result = await api.random_word()
print(result)
```

#### Expected Output

```text
rationality
```

### 21. Riddle

**Description**:
Fetches a random riddle from the Riddles API.

**Returns:**
  - **dict**: The riddle data in JSON format.

```python
from TheApi import api

result = await api.riddle()
print(result)
```

#### Expected Output

```json
{
    "riddle": "I am the creator, through thick and thin, My time is sunset then I begin. Worlds of men and beasts I make, to me these things are not fake. But Over and over I will kill , I am the tirent and creator but not at will. What am I?",
    "answer": "A sleeping dreamer"
}
```

### 22. Stackoverflow Search

**Description**:
Searches Stack Overflow for questions based on a query, returning results sorted by relevance or another specified criteria.

**Args:**
  - **query (str)**: The search query string.
  - **max_results (int, optional)**: The maximum number of results to return. Defaults to 3.
  - **sort_type (str, optional)**: The sorting criteria for the results, such as "relevance" or "votes". Defaults to "relevance".

**Returns:**
  - **list**: A list of search results in JSON format, with each entry containing Stack Overflow question details.

**Raises:**
  - **ValueError**: If there is an issue with the request to the Stack Overflow API.

```python
from TheApi import api

result = await api.stackoverflow_search(query='Pokemon', max_results=3, sort_type='relevance')
print(result)
```

#### Expected Output

```json
[
    {
        "tags": [
            "ios",
            "flutter",
            "dart"
        ],
        "owner": {
            "account_id": 19921816,
            "reputation": 3,
            "user_id": 14597469,
            "user_type": "registered",
            "profile_image": "https://lh6.googleusercontent.com/-aT6u2l_JT94/AAAAAAAAAAI/AAAAAAAAAAA/AMZuuclcxb94zp_q0Q2R8DQN7b6X3kgo6w/s96-c/photo.jpg?sz=256",
            "display_name": "Senem Sedef",
            "link": "https://stackoverflow.com/users/14597469/senem-sedef"
        },
        "is_answered": false,
        "view_count": 117,
        "answer_count": 0,
        "score": 0,
        "last_activity_date": 1701515081,
        "creation_date": 1622231772,
        "last_edit_date": 1701515081,
        "question_id": 67744802,
        "content_license": "CC BY-SA 4.0",
        "link": "https://stackoverflow.com/questions/67744802/the-getter-pokemon-was-called-on-null-receiver-null-tried-calling-pokemon",
        "title": "The getter &#39;pokemon&#39; was called on null. Receiver: null Tried calling: pokemon"
    },
    {
        "tags": [
            "reactjs",
            "random",
            "axios"
        ],
        "owner": {
            "account_id": 17931576,
            "reputation": 1,
            "user_id": 13028884,
            "user_type": "registered",
            "profile_image": "https://www.gravatar.com/avatar/7ebcdd2f784bca5dc54a1a0e17354f86?s=256&d=identicon&r=PG&f=y&so-version=2",
            "display_name": "GieGie",
            "link": "https://stackoverflow.com/users/13028884/giegie"
        },
        "is_answered": false,
        "view_count": 1971,
        "answer_count": 2,
        "score": 0,
        "last_activity_date": 1652730812,
        "creation_date": 1642222168,
        "last_edit_date": 1642223800,
        "question_id": 70718940,
        "content_license": "CC BY-SA 4.0",
        "link": "https://stackoverflow.com/questions/70718940/pokemon-api-request-generate-5-pok%c3%a9mon-at-a-time",
        "title": "Pokemon API request generate 5 Pok&#233;mon at a time"
    },
    {
        "tags": [
            "java"
        ],
        "owner": {
            "account_id": 919945,
            "reputation": 43,
            "user_id": 951797,
            "user_type": "registered",
            "profile_image": "https://www.gravatar.com/avatar/26b06d5d95992fa3780383abe5f49a3d?s=256&d=identicon&r=PG",
            "display_name": "Brian",
            "link": "https://stackoverflow.com/users/951797/brian"
        },
        "is_answered": true,
        "view_count": 32633,
        "accepted_answer_id": 7942409,
        "answer_count": 3,
        "score": 3,
        "last_activity_date": 1577442848,
        "creation_date": 1319931614,
        "question_id": 7942384,
        "content_license": "CC BY-SA 3.0",
        "link": "https://stackoverflow.com/questions/7942384/simple-java-pokemon-fight-simulator",
        "title": "Simple Java Pokemon Fight Simulator"
    }
]
```

### 23. Upload Image

**Description**:
Uploads an image to https://envs.sh.

**Args:**
  - **file_path (Union[str, bytes, BytesIO])**: The image file to upload.
    Can be a file path (str), binary data (bytes), or a BytesIO object.

**Returns:**
  - **str**: The URL or confirmation message of the uploaded image if the upload is successful.
    Returns "Unexpected response format" if the response format is not as expected.

**Raises:**
  - **ValueError**: If the file is not found, the input type is invalid,
    or the upload request fails.

```python
from TheApi import api

result = await api.upload_image(file_path='file/to/upload')
print(result)
```

#### Expected Output

```text
You will get a URL
```

### 24. Wikipedia

**Description**:
Searches Wikipedia for a given query and retrieves the top result's summary, URL, and image.

**Args:**
  - **query (str)**: The search term to look up on Wikipedia.

**Returns:**
  - **dict**: A dictionary containing information about the top search result, with keys:
    - title (str): The title of the Wikipedia article.
    - summary (str): A brief summary of the article's content.
    - url (str): The URL link to the full Wikipedia article.
    - image_url (str): The URL of the article's thumbnail image, or "No image available" if none exists.

**Description**:
If no results are found, returns a dictionary with an "error" key.

```python
from TheApi import api

result = await api.wikipedia(query='Pokemon')
print(result)
```

#### Expected Output

```json
{
    "title": "Pok\u00e9mon",
    "summary": "Pok\u00e9mon is a Japanese media franchise consisting of video games, animated series and films, a trading card game, and other related media. The franchise takes place in a shared universe in which humans co-exist with creatures known as Pok\u00e9mon, a large variety of species endowed with special powers. The franchise's target audience is children aged 5 to 12, but it is known to attract people of all ages.\nThe franchise originated as a pair of role-playing games developed by Game Freak, from an original concept by its founder, Satoshi Tajiri. Released on the Game Boy on February 27, 1996, the games became sleeper hits and were followed by manga series, a trading card game, and anime series and films. From 1998 to 2000, Pok\u00e9mon was exported to the rest of the world, creating an unprecedented global phenomenon dubbed \"Pok\u00e9mania\". By 2002, the craze had ended, after which Pok\u00e9mon became a fixture in popular culture, with new products being released to this day. In the summer of 2016, the franchise spawned a second craze with the release of Pok\u00e9mon Go, an augmented reality game developed by Niantic. Pok\u00e9mon has since been estimated to be the world's highest-grossing media franchise and one of the best-selling video game franchises.\nPok\u00e9mon has an uncommon ownership structure. Unlike most IPs, which are owned by one company, Pok\u00e9mon is jointly owned by three: Nintendo, Game Freak, and Creatures. Game Freak develops the core series role-playing games, which are published by Nintendo exclusively for their consoles, while Creatures manages the trading card game and related merchandise, occasionally developing spin-off titles. The three companies established The Pok\u00e9mon Company (TPC) in 1998 to manage the Pok\u00e9mon property within Asia. The Pok\u00e9mon anime series and films are co-owned by Shogakukan. Since 2009, The Pok\u00e9mon Company International (TPCi), a subsidiary of TPC, has managed the franchise in all regions outside of Asia.\n\n",
    "url": "https://en.wikipedia.org/?curid=23745",
    "image_url": "https://upload.wikimedia.org/wikipedia/commons/thumb/9/98/International_Pok%C3%A9mon_logo.svg/500px-International_Pok%C3%A9mon_logo.svg.png"
}
```

### 25. Words

**Description**:
Fetches a specified number of random words.

**Args:**
  - **num_words (int)**: The number of random words to retrieve.

**Returns:**
  - **list**: A list of random words if available; an empty list if no response is received.

```python
from TheApi import api

result = await api.words(num_words=5)
print(result)
```

#### Expected Output

```text
journalizing
aggrade
redetermination
birdings
merit
```

### 26. Write

**Description**:
Creates an image with text written on it, using a predefined template and font, and uploads the image after generation.

**Args:**
  - **text (str)**: The text to be written on the image. Text exceeding 55 characters
    per line will be wrapped, with up to 25 lines displayed.

**Returns:**
  - **str**: The URL of the uploaded image.

**Description**:
Notes: A temporary image file is created, saved, and removed after uploading.

```python
from TheApi import api

result = await api.write(text='Pokemon')
print(result)
```

#### Expected Output

```text
/home/runner/work/TheApi/TheApi/downloads/write_oTHtt6s8.jpg
```


This Project is Licensed under [MIT License](https://github.com/Vivekkumar-IN/TheApi/blob/main/LICENSE)