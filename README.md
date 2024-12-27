Welcome to the **TheApix!** This library allows you to easily interact with the API using asynchronous options.

#### Installation

```sh
pip install TheApix
```

##### FilePath Class
The `FilePath` class is a wrapper around a file path string, adding an additional `delete()` method to handle file deletion.

```python
class FilePath(str):
    """
    A wrapper around a file path string that provides an additional delete method.

    Attributes:
        path (str): The file path to the media file.

    Methods:
        delete(): Attempts to delete the file at the specified path.
                  If deletion fails, it handles the exception gracefully.
    """

    def delete(self):
        """Deletes the file at the specified path, handling exceptions if deletion fails."""
        try:
            os.remove(self)
        except Exception:
            pass
```

##### Usage Example

Whenever a media path is returned, it will be wrapped in a `FilePath` object. You can then call `delete()` on that object to delete the file if it exists.

```python
from TheApi import api

# Example of using the API to get a file path
file_path = await api.blackpink(query='Pokemon')  # Returns the file path where the blackpink media is saved

print(file_path)  # Print the file path

file_path.delete()  # Delete the file if it exists
```

In the example above, `file_path` will be an instance of the `FilePath` class, which allows you to easily delete the file associated with the media once you are done with it.

---

# 📘 API Documentation

## Status

| Function           | Status |
|--------------------|--------|
| [1. Animechan](#1-animechan) | ✅
| [2. Avatar](#2-avatar) | ✅
| [3. Bing Image](#3-bing-image) | ✅
| [4. Blackpink](#4-blackpink) | ✅
| [5. Carbon](#5-carbon) | ✅
| [6. Cat](#6-cat) | ✅
| [7. Dog](#7-dog) | ✅
| [8. Domain Search](#8-domain-search) | ❌
| [9. Fakerapi](#9-fakerapi) | ❌
| [10. Fox](#10-fox) | ✅
| [11. Gen Qr](#11-gen-qr) | ✅
| [12. Generate Pdf](#12-generate-pdf) | ✅
| [13. Get Advice](#13-get-advice) | ✅
| [14. Get Btc Value](#14-get-btc-value) | ✅
| [15. Get Fake Addresses](#15-get-fake-addresses) | ✅
| [16. Get Fake Credit Cards](#16-get-fake-credit-cards) | ✅
| [17. Get Fake Images](#17-get-fake-images) | ✅
| [18. Get Hindi Jokes](#18-get-hindi-jokes) | ✅
| [19. Get Jokes](#19-get-jokes) | ✅
| [20. Get Uselessfact](#20-get-uselessfact) | ✅
| [21. Get Word Definitions](#21-get-word-definitions) | ✅
| [22. Get Words](#22-get-words) | ✅
| [23. Github Search](#23-github-search) | ✅
| [24. Hindi Quote](#24-hindi-quote) | ✅
| [25. Hug](#25-hug) | ✅
| [26. Meme](#26-meme) | ✅
| [27. Neko](#27-neko) | ✅
| [28. Pypi](#28-pypi) | ✅
| [29. Quote](#29-quote) | ✅
| [30. Riddle](#30-riddle) | ✅
| [31. Stackoverflow Search](#31-stackoverflow-search) | ✅
| [32. Upload Image](#32-upload-image) | ✅
| [33. Wikipedia](#33-wikipedia) | ✅
| [34. Write](#34-write) | ✅


## 🎓 How to Use Each Function

### 1. Animechan

**Description**:
Fetches a random anime quote from the AnimeChan API.

**Returns:**
  - **dict**: Contains the quote content, anime name, and character details.

```python
from Pokemon import api

result = await api.animechan()
print(result)
```

#### Expected Output

```json
{
    "content": "I always wanted to become stronger. At first it was to protect myself. Next, it was to protect Hak, who gave up everything for me. Now, it's to repay my friends, who enabled me to live.",
    "anime": {
        "id": 327,
        "name": "Yona of the Dawn",
        "altName": "Akatsuki no Yona"
    },
    "character": {
        "id": 415,
        "name": "Yona"
    }
}
```

### 2. Avatar

**Description**:
Fetches a random avatars from the thedobby.club API.

**Returns:**
  - **dict**: Contains the file name, file type, and file URL.

```python
from Pokemon import api

result = await api.avatar()
print(result)
```

#### Expected Output

```json
{
    "file_name": "sara",
    "file_type": "image/jpeg",
    "file_url": "https://cofuvfbkdyfchroaxcvi.supabase.co/storage/v1/object/public/avatars/sara.jpg"
}
```

### 3. Bing Image

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
https://assets-prd.ignimgs.com/2021/03/01/new-pokemon-snap-button-1614639848584.jpg
https://img-eshop.cdn.nintendo.net/i/00bd7efe46ab2b3ff0774172a5d4f21a5b2f467b3e324557ce1e9a9ae12c1d3b.jpg
https://assets.rpgsite.net/images/images/000/096/196/original/New-Pokemon-Snap_20210226_07.jpg
https://images.launchbox-app.com/1f06f096-8eb6-43ac-abbb-262deb1bf596.jpg
https://media.gamestop.com/i/gamestop/11103360/New-Pokemon-Snap---Nintendo-Switch
https://www.nme.com/wp-content/uploads/2021/05/New-Pokemon-Snap-Credit-Bandai-Namco-HERO@2000x1270.jpg
https://cdn.mobilesyrup.com/wp-content/uploads/2021/01/new-pokemon-snap-screenshot-2.jpg
https://cdn.vox-cdn.com/thumbor/Lgiz7lrS_auxnKixNMsWmsx_ETE=/1400x788/filters:format(jpeg)/cdn.vox-cdn.com/uploads/chorus_asset/file/22473880/Switch_NewPokemonSnap_Screenshots_Feb26__9_.jpg
https://webgames.host/uploads/2017/09/pokemon-snap.jpg
https://www.videogamer.com/wp-content/uploads/01d7162d-749b-43eb-bdcc-5c0cf9e49881_New_Pokmon_Snap_Main.jpg
https://cdn.mos.cms.futurecdn.net/4QhbnUhVrk8GG8uUGDZASd.jpg
https://media.npr.org/assets/img/2021/04/29/snap-1_wide-7c41973fe9eef7cbc49beec9a59f3bf5410187d2-s1400-c100.jpg
https://www.lukiegames.com/assets/images/N64/n64_pokemon_snap_p_66pv3n.jpg
https://www.gamespot.com/a/uploads/screen_kubrick/123/1239113/3801204-6238037227-screenshot02.jpg
https://www.nme.com/wp-content/uploads/2022/06/Pokemon-Snap-64-2000x1270-1.jpg
https://i.gadgets360cdn.com/products/large/New-Pokemon-Snap-Wallpaper-1440x2560-1000x1778-1646977124.jpg
https://www.weplay.cl/pub/media/catalog/product/cache/3f1b140c3c9f36fbf6b01dffb521c246/p/r/producto24286_1.jpg
https://www.nintendo.com/sg/switch/arft/img/hero_sp.jpg
https://images.launchbox-app.com/fc92b8c7-704f-43e9-ab5a-407b712bc662.jpg
https://www.gamespot.com/a/uploads/original/1552/15524586/3824788-ahtqudcvxe2lb3q8kqx55m.jpeg
https://twinfinite.net/wp-content/uploads/2019/09/PokemonTypes.png
https://upload.wikimedia.org/wikipedia/commons/thumb/9/97/Pokemon_Type_Chart.svg/2048px-Pokemon_Type_Chart.svg.png
https://pokeguide.neocities.org/Pic/pokemontype.png
https://releasegaming.com/wp-content/uploads/2023/02/Pokemon-Type-Chart-Poster-960x850.jpg
http://res.cloudinary.com/lmn/image/upload/e_sharpen:150,f_auto,fl_lossy,q_80/v1/gameskinnyc/p/o/k/pokemon-types-table-ad163.png
https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/472f4a44-0b68-46a9-bfd1-ffca5f5d411f/dbnh54g-993f09cd-8bc1-4653-86e3-5ca28b95e8a9.png/v1/fill/w_1024,h_724/_pokemon__38_types_by_wergan_dbnh54g-fullview.png?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7ImhlaWdodCI6Ijw9NzI0IiwicGF0aCI6IlwvZlwvNDcyZjRhNDQtMGI2OC00NmE5LWJmZDEtZmZjYTVmNWQ0MTFmXC9kYm5oNTRnLTk5M2YwOWNkLThiYzEtNDY1My04NmUzLTVjYTI4Yjk1ZThhOS5wbmciLCJ3aWR0aCI6Ijw9MTAyNCJ9XV0sImF1ZCI6WyJ1cm46c2VydmljZTppbWFnZS5vcGVyYXRpb25zIl19.8ikZ0Io3pDkjQ1bahvU_ux81ssIRvgztcDY_M3RiaIs
https://videogamesuncovered.com/wp-content/uploads/2016/12/pokemon-types.jpg
https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/7b386f5f-9a3f-497c-ad22-b2b574b05b37/dfdt5ai-9bb7a5ee-e8a4-4c02-8054-d2cad2c6587c.png?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7InBhdGgiOiJcL2ZcLzdiMzg2ZjVmLTlhM2YtNDk3Yy1hZDIyLWIyYjU3NGIwNWIzN1wvZGZkdDVhaS05YmI3YTVlZS1lOGE0LTRjMDItODA1NC1kMmNhZDJjNjU4N2MucG5nIn1dXSwiYXVkIjpbInVybjpzZXJ2aWNlOmZpbGUuZG93bmxvYWQiXX0.FLSo4mjTVTJlbSUvakBka2x4IQduRxJYNS9rfwHrPnk
http://img.pokemondb.net/images/typechart.png
https://cdn1.vectorstock.com/i/1000x1000/03/95/pokemon-type-symbols-vector-2700395.jpg
https://www.mandatory.gg/wp-content/uploads/mandatory-guide-pokemon-ecarlate-violet-table-types-forces-faiblesses.png
https://raw.githubusercontent.com/kennycason/cellular-automata-pokemon-types/master/data/pokemon_gen1_type_chart.png?raw=true
https://www.theloadout.com/wp-content/sites/theloadout/2023/06/pokemon-type-chart-icons.jpg
https://img00.deviantart.net/4c45/i/2012/137/8/6/pokemon_type_chart_by_the_bent_one-d30zwry.png
https://1.bp.blogspot.com/-A0NsVJu2Ay0/WGOgGNxAdTI/AAAAAAAABIY/amMTic8SsXYs7jfP_ITwBmkeVQHIAGZ-ACPcB/s1600/ENG-05-02-02-All-the-Pokemon-types.png
https://www.pngitem.com/pimgs/m/510-5102094_http-image-noelshack-pokemon-artefact-all-types-pokemon.png
http://1.bp.blogspot.com/-m_64koMO6IU/VWM8SWNwUBI/AAAAAAAAAfQ/r33Sbq0xJtg/s1600/pokemon_types_wheel_by_kamionero-d6u6o9i.png
https://i.pinimg.com/originals/3c/56/1d/3c561dc2733cad1da67f39c5cf7718f2.png
http://i.imgur.com/OdoUgES.jpg
https://vignette3.wikia.nocookie.net/pokemonadventure/images/a/ad/Symbols.png/revision/latest?cb=20121003192408
https://mlpnk72yciwc.i.optimole.com/cqhiHLc.WqA8~2eefa/w:auto/h:auto/q:75/https://bleedingcool.com/wp-content/uploads/2020/06/Charizard-grade-9-mint-front.jpg
https://images.saymedia-content.com/.image/t_share/MTc5ODE2MjE2Mjc2NDQ0Nzgz/best-v-pokemon-cards.jpg
https://imgix.ranker.com/user_node_img/3181/63618188/original/blastoise-u16?fit=crop&amp;fm=pjpg&amp;q=60&amp;w=650&amp;dpr=2
https://i.etsystatic.com/22464198/r/il/92a686/2662042144/il_1140xN.2662042144_ns4d.jpg
https://images.saymedia-content.com/.image/t_share/MTgzNzE1NDA2MDk0MDE3ODU1/best-vmax-pokemon-cards.png
https://i.pinimg.com/736x/83/e3/5a/83e35aead31fabb77b9bde3396d4351f.jpg
https://i.etsystatic.com/21027128/r/il/fdbdba/2003255292/il_1588xN.2003255292_12o2.jpg
https://www.oldsportscards.com/wp-content/uploads/2019/12/Most-Valuable-First-Edition-Pokemon-Cards.jpg
https://www.pokemoncenter.com/products/images/P2373PC/155-80156/P2373PC_155-80156_01.jpg
https://i.etsystatic.com/23914535/r/il/750695/2869449405/il_1588xN.2869449405_fr75.jpg
https://pm1.narvii.com/6267/3e8dabe202aa4911724963a0eb1b1f0b0c875193_hq.jpg
https://i.pinimg.com/originals/71/ef/f5/71eff5e6a94ac98d3d6c39c8f9d0221d.jpg
https://i.etsystatic.com/24353291/r/il/358485/2689751041/il_fullxfull.2689751041_ofmo.jpg
https://i2.wp.com/nypost.com/wp-content/uploads/sites/2/2020/12/pokemon-auction.jpg?quality=90&amp;strip=all&amp;ssl=1
https://miro.medium.com/max/1400/1*I9DUHexc5eoKn1-dZs4g0A.jpeg
https://m.media-amazon.com/images/I/91lXJ99OooL.jpg
https://cdn11.bigcommerce.com/s-0kvv9/images/stencil/1920w/products/371952/569692/pokemonevolvingskies041__83278.1630015209.jpg?c=2
https://i.etsystatic.com/22089514/r/il/ecff88/4140836231/il_fullxfull.4140836231_cpmu.jpg
https://www.printablee.com/postpic/2014/04/rare-pokemon-cards-printable_23606.jpg
https://www.printablee.com/postpic/2013/12/rare-pokemon-cards-printable_23336.jpg
https://townsquare.media/site/622/files/2016/08/poke-feat.jpg?w=1200&amp;h=0&amp;zc=1&amp;s=0&amp;a=t&amp;q=89
https://static3.cbrimages.com/wordpress/wp-content/uploads/2019/09/Pokemon-Ash-Feature-Image-1.jpg
https://upload.wikimedia.org/wikipedia/en/thumb/9/9e/150_Pokemon_from_Pokemon_Stadium.png/330px-150_Pokemon_from_Pokemon_Stadium.png
```

### 4. Blackpink

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
downloads/blackpink_LhKiupWu.jpg
```

### 5. Carbon

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
downloads/carbon_z67Yr46Y.png
```

### 6. Cat

**Description**:
Fetches a random cat image URL.

**Returns:**
  - **str or None**: The URL of a random cat image if available; None if no response is received.

```python
from Pokemon import api

result = await api.cat()
print(result)
```

#### Expected Output

```text
https://cdn2.thecatapi.com/images/MTk2OTMyNw.jpg
```

### 7. Dog

**Description**:
Fetches a random dog image URL.

**Returns:**
  - **str or None**: The URL of a random dog image if available; None if no response is received.

```python
from Pokemon import api

result = await api.dog()
print(result)
```

#### Expected Output

```text
https://random.dog/98e2e1f3-5d5a-4d1a-b155-a37fe304468e.mp4
```

### 8. Domain Search

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

```text
Expecting value: line 1 column 1 (char 0)
```

### 9. Fakerapi

**Description**:
Fetch data from the FakerAPI using aiohttp.

**Args:**
  - **endpoint (str)**: The resource endpoint. Valid endpoints are:
    - companies
    - addresses
    - books
    - CreditCards
    - images
    - persons
    - places
    - products
    - texts
    - users

**Description**:
quantity (int, optional): Number of rows to fetch (default: 3, max: 1000). locale (str, optional): Locale for the data (default: 'en_US').  [ See Valid locale ](https://fakerapi.it/#params_locale)

**Raises:**
  - **ValueError**: If the locale is invalid, the endpoint is invalid, or the quantity
    is outside the allowed range.

**Returns:**
  - **dict**: Response data from the API.


### 10. Fox

**Description**:
Fetches a random fox image URL.

**Returns:**
  - **str or None**: The URL of the fox image if available, otherwise None.

```python
from Pokemon import api

result = await api.fox()
print(result)
```

#### Expected Output

```text
https://randomfox.ca/?i=25
```

### 11. Gen Qr

**Description**:
Generate a QR code using api.qrserver.com and save it as a PNG file.

**Args:**
  - **data (str)**: The content for the QR code.
  - **size (str)**: The size of the QR code in the format 'WIDTHxHEIGHT' (default: '150x150').
  - **foreground_color (str)**: The color of the QR code (default: '000000' - black).
  - **background_color (str)**: The background color of the QR code (default: 'FFFFFF' - white).

**Returns:**
  - **FilePath**: The file path where the QR code was saved.

```python
from TheApi import api

result = await api.gen_qr(data='Pokemon', size='150x150', foreground_color='000000', background_color='FFFFFF')
print(result)
```

#### Expected Output

```text
downloads/QrCode_EujjawDn.png
```

### 12. Generate Pdf

**Description**:
Generates a PDF from a URL or an HTML string and saves it to a file.

**Args:**
  - **source (str)**: The URL of the website (if `from_url=True`) or the HTML string (if `from_url=False`).
  - **from_url (bool, optional)**: Whether to generate the PDF from a URL (True) or an HTML string (False).

**Returns:**
  - **FilePath**: The file path where the PDF was saved.

**Raises:**
  - **ValueError**: If `from_url` is True and `source` is not a valid URL.


### 13. Get Advice

**Description**:
Fetches a random piece of advice.

**Returns:**
  - **str**: A random advice message.

```python
from Pokemon import api

result = await api.get_advice()
print(result)
```

#### Expected Output

```text
Mercy is the better part of justice.
```

### 14. Get Btc Value

**Description**:
Fetches the current value of Bitcoin (BTC) for the specified currency or all currencies.

**Args:**
  - **currency (str, optional)**: The currency code (e.g., 'eur', 'usd', 'gbp').
    If None, fetches BTC value for all currencies.

**Returns:**
  - **dict**: The response containing BTC value(s) for the specified currency or all currencies.

**Raises:**
  - **ValueError**: If the provided currency is invalid or the request fails.

```python
from TheApi import api

result = await api.get_btc_value(currency=None)
print(result)
```

#### Expected Output

```json
{
    "EUR": {
        "code": "EUR",
        "description": "Euro",
        "rate": "92,473.505",
        "rate_float": 92473.5054,
        "symbol": "&euro;"
    },
    "GBP": {
        "code": "GBP",
        "description": "British Pound Sterling",
        "rate": "76,868.877",
        "rate_float": 76868.8767,
        "symbol": "&pound;"
    },
    "USD": {
        "code": "USD",
        "description": "United States Dollar",
        "rate": "96,389.724",
        "rate_float": 96389.7235,
        "symbol": "&#36;"
    }
}
```

### 15. Get Fake Addresses

**Description**:
Fetch fake address data from the FakerAPI.

**Args:**
  - **quantity (int, optional)**: Number of address entries to fetch (default: 1).
  - **locale (str, optional)**: Locale for the address data (default: "en_US"), [ See Valid locale ](https://fakerapi.it/#params_locale).

**Returns:**
  - **dict**: Response data from the API.

```python
from TheApi import api

result = await api.get_fake_addresses(quantity=1, locale='en_US')
print(result)
```

#### Expected Output

```json
{
    "status": "OK",
    "code": 200,
    "locale": "en_US",
    "seed": null,
    "total": 1,
    "data": [
        {
            "id": 1,
            "street": "1834 Zola Centers",
            "streetName": "Keeling Roads",
            "buildingNumber": "740",
            "city": "New Mortonberg",
            "zipcode": "20104-0885",
            "country": "Puerto Rico",
            "country_code": "PR",
            "latitude": -76.438733,
            "longitude": 58.468418
        }
    ]
}
```

### 16. Get Fake Credit Cards

**Description**:
Fetch fake credit card data from the FakerAPI.

**Args:**
  - **locale (str, optional)**: Locale for the credit card data (default: "en_US"), [ See Valid locale ](https://fakerapi.it/#params_locale).
  - **amount (int, optional)**: Number of credit card entries to fetch (default: 1).

**Returns:**
  - **dict**: Response data from the API.

```python
from TheApi import api

result = await api.get_fake_credit_cards(locale='en_US', quantity=1)
print(result)
```

#### Expected Output

```json
{
    "status": "OK",
    "code": 200,
    "locale": "en_US",
    "seed": null,
    "total": 1,
    "data": [
        {
            "type": "Visa",
            "number": "4929349768578",
            "expiration": "01/25",
            "owner": "Leanna Trantow"
        }
    ]
}
```

### 17. Get Fake Images

**Description**:
Fetch fake image data from the FakerAPI.

**Args:**
  - **quantity (int, optional)**: Number of images to fetch (default: 1).
  - **locale (str, optional)**: Locale for the images (default: "en_US"), [ See Valid locale ](https://fakerapi.it/#params_locale).
  - **type (str, optional)**: Type of image (e.g., 'any', 'animals', 'business', etc.; default: "any").
  - **width (int, optional)**: Width of the images (default: 640).
  - **height (int, optional)**: Height of the images (default: 480).

**Returns:**
  - **dict**: Response data from the API.

```python
from TheApi import api

result = await api.get_fake_images(quantity=1, locale='en_US', type='any', width=640, height=480)
print(result)
```

#### Expected Output

```json
{
    "status": "OK",
    "code": 200,
    "locale": "en_US",
    "seed": null,
    "total": 1,
    "data": [
        {
            "title": "Eaque qui facere rerum dicta.",
            "description": "Deserunt quis et cupiditate at odio. Nemo qui ipsa ab officiis rerum debitis consequatur. Sit molestiae velit atque dolores repudiandae. Et perferendis autem minus quas omnis esse ut suscipit.",
            "url": "https://picsum.photos/640/480"
        }
    ]
}
```

### 18. Get Hindi Jokes

**Description**:
Fetches a random Hindi joke.

**Returns:**
  - **str**: A random Hindi joke if available, or "No joke found" if not available.

```python
from Pokemon import api

result = await api.get_hindi_jokes()
print(result)
```

#### Expected Output

```text
पति को बाजार जाते हुए देख पत्नी ने पैसे देकर कहा  कुछ ऐसी चीज़ लाना जिस से मैं सुन्दर दिखूं  👗👓💄👠🎀 पति खुद के लिए Whisky की दो बोतल ले आया। 😜😃
```

### 19. Get Jokes

**Description**:
Fetches a specified number of jokes.

**Args:**
  - **amount (int, optional)**: The number of jokes to retrieve. Defaults to 1.

**Returns:**
  - **str**: A single joke if `amount` is 1.
  - **list**: If `amount` > 1, returns numbered jokes.

```python
from TheApi import api

result = await api.get_jokes(amount=1)
print(result)
```

#### Expected Output

```text
Stop being homophobic and rude to the LGBTQ+ community. You should be thanking them for saving us plenty of room in heaven.
```

### 20. Get Uselessfact

**Description**:
Fetches a random useless fact.

**Returns:**
  - **str**: A random useless fact.

```python
from Pokemon import api

result = await api.get_uselessfact()
print(result)
```

#### Expected Output

```text
The Vatican city registered 0 births in 1983
```

### 21. Get Word Definitions

**Description**:
Fetch definitions for a word from the Dictionary API.

**Args:**
  - **word (str)**: The word to fetch definitions for.

**Returns:**
  - **list**: A list of dictionaries containing the word definitions.

**Raises:**
  - **ValueError**: If the `word` is not provided or the API request fails.

```python
from TheApi import api

result = await api.get_word_definitions(word='Pokemon')
print(result)
```

#### Expected Output

```json
{
    "title": "No Definitions Found",
    "message": "Sorry pal, we couldn't find definitions for the word you were looking for.",
    "resolution": "You can try the search again at later time or head to the web instead."
}
```

### 22. Get Words

**Description**:
Fetch random words from the Random Word API.

**Args:**
  - **words (int)**: Number of words to generate (default is 10).
  - **letter (str)**: First letter of the words (optional).
  - **word_type (str)**: Type of words (lowercase, uppercase, capitalized; default is capitalized).
  - **alphabetize (bool)**: Whether to alphabetize the result (default is False).

**Returns:**
  - **list**: A list of random words or an error message.

```python
from TheApi import api

result = await api.get_words(words=10, letter=None, word_type='capitalized', alphabetize=False)
print(result)
```

#### Expected Output

```text
Attic
Patronize
Commerce
Thriving
Unloved
Bullseye
Coaster
Kerosene
Prepaid
Handwoven
```

### 23. Github Search

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
        "stargazers_count": 7526,
        "forks_count": 2815
    },
    {
        "name": "pokemon-showdown",
        "full_name": "smogon/pokemon-showdown",
        "description": "Pok\u00e9mon battle simulator.",
        "url": "https://github.com/smogon/pokemon-showdown",
        "language": "TypeScript",
        "stargazers_count": 4838,
        "forks_count": 2828
    },
    {
        "name": "PokemonGo-Bot",
        "full_name": "PokemonGoF/PokemonGo-Bot",
        "description": "The Pokemon Go Bot, baking with community.",
        "url": "https://github.com/PokemonGoF/PokemonGo-Bot",
        "language": "Python",
        "stargazers_count": 3880,
        "forks_count": 1542
    }
]
```

### 24. Hindi Quote

**Description**:
Fetches a random Hindi quote.

**Returns:**
  - **str**: The content of a random Hindi quote.

```python
from Pokemon import api

result = await api.hindi_quote()
print(result)
```

#### Expected Output

```text
राह संघर्ष की जो चलता है; वो ही संसार को बदलता है, जिसने रातों से जंग जीती, सूर्य बनकर वहीं निकलता है।
```

### 25. Hug

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
        "anime_name": "Princess Connect! Re:Dive",
        "url": "https://nekos.best/api/v2/hug/85e51199-6829-4ffd-85e3-4d1a1b9ba891.gif"
    }
]
```

### 26. Meme

**Description**:
Fetches a random meme image URL.

**Returns:**
  - **str or None**: The URL of the meme image if available, otherwise None.

```python
from Pokemon import api

result = await api.meme()
print(result)
```

#### Expected Output

```text
https://preview.redd.it/81hs67rzos8e1.png?width=640&crop=smart&auto=webp&s=93b9abc898aa141bcda00df1d5d04ac070c78766
```

### 27. Neko

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
            "artist_href": "https://www.pixiv.net/en/users/82002228",
            "artist_name": "\u3042\u305a\u8449",
            "source_url": "https://www.pixiv.net/en/artworks/99961696",
            "url": "https://nekos.best/api/v2/neko/7e7d91ae-d984-42be-9e5a-92a3eb64574f.png"
        },
        {
            "artist_href": "https://twitter.com/ameto_y",
            "artist_name": "ameto_y",
            "source_url": "https://twitter.com/i/web/status/943392983172263936",
            "url": "https://nekos.best/api/v2/neko/f47ec074-ba04-4215-be17-a5b7ee4f2c15.png"
        },
        {
            "artist_href": "https://www.pixiv.net/en/users/979076",
            "artist_name": "Chloette",
            "source_url": "https://www.pixiv.net/en/artworks/100313351",
            "url": "https://nekos.best/api/v2/neko/f0740af8-4dcb-44d4-8b8a-1e9545f62735.png"
        }
    ]
}
```

### 28. Pypi

**Description**:
Retrieves metadata information about a specified Python package from the PyPI API.

**Args:**
  - **package_name (str)**: The name of the package to search for on PyPI.

**Returns:**
  - **dict or None**: A dictionary with relevant package information if found.
    Returns None if the package is not found or there is an error.

```python
from TheApi import api

result = await api.pypi(package_name='Pokemon')
print(result)
```

#### Expected Output

```json
{
    "info": {
        "author": "Vanessa Sochat",
        "author_email": "vsoch@noreply.github.users.com",
        "bugtrack_url": null,
        "classifiers": [],
        "description": "# pokemon\n\nWatch the pokemon ascii being born!\n\n![img/generation.gif](https://github.com/vsoch/pokemon/raw/master/img/generation.gif)\n\nThis is a module for generating ascii art for any of the 890 pokemon, across 8 generations, in the Pokedex. The package includes functions for generating \"gravatars\" (pokemon associated with an identifier like an email address), and functions for searching and exploring the database. The library includes a [version of the database](pokemon/database/db.json) generated with [pokemon/make_db.py](pokemon/make_db.py) that can be updated by re-running the script. The choice of ascii art is to produce pokemon images or avatars that are suited for command line tools.\n\n```bash\n$ pokemon\nusage: pokemon [-h] [--avatar AVATAR] [--pokemon POKEMON] [--message MESSAGE]\n               [--catch] [--list]\n\ngenerate pokemon ascii art and avatars\n\noptional arguments:\n  -h, --help         show this help message and exit\n  --avatar AVATAR    generate a pokemon avatar for some unique id.\n  --pokemon POKEMON  generate ascii for a particular pokemon (by name)\n  --message MESSAGE  add a custom message to your ascii!\n  --catch            catch a random pokemon!\n  --list             list pokemon available\n```\n\n## Installation\n\nYou can install directly from pip:\n\n```bash\n$ pip install pokemon\n```\n\nor for the development version, clone the repo and install manually:\n\n```bash\ngit clone https://github.com/vsoch/pokemon\ncd pokemon\npip install .\n```\n\n## Produce an avatar\n\nAn \"avatar\" is an image that is consistently associated with some unique ID. In our case, this is an ascii avatar. For example,\n\n![img/avatar.png](img/avatar.png)\n\nTo do this, I take the hash of a string, and then use modulus to get the remainder of that hash divided by the number of pokemon in the database. This means that, given that the database doesn't change, and given that the pokemon have unique IDs in the range of 1 to 721, you should always get the same image for some unique id (like an email).\n\n**Note** the database was updated between version 0.34 and version 0.35, so you will\nget different avatars depending on the version you are using. There are Docker tags\nand pip installs available for each, and version 0.35 is suggested to use with Python 3.\n\n```bash\n$ pokemon --avatar vsoch\n\n@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@\n@@@@@@@@@?:::::::::::::::+.+.@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@\n@@@@@@@*?%:::::::::*::****#SSSSS%.**S+@@@@@@@@@@@@@@@@@@@@@@\n@@@@@@@*???:::::::*********#...+****++++S:@@@@@@@@@@@@@@@@@@\n@@@@@@@::SSS............S+.*....*****?%S+#@@@@@@@@@@@@@@@@@@\n@@@@@@@@@@@@@@.?SS.S.....S?%%%%%%%%..**+....?@@@@@@@@@@@@@@@\n@@@@@@@@@@@@@@@@..%???????#%%%%%%%....**++.....?@@@@@@@@@@@@\n@@@@@@@@@@@@@@..+++%????????????%%%%%%*.......%++%@@@@@@@@@@\n@@@@@@@@@@@@S.+++++S%+++SS%..????%%%?..............@@@@@@@@@\n@@@@@@@@@@@%++++S+S++++.......?@%%%%%......SSSSSS:@@@@@@@@@@\n@@@@@@@@@?.++.+++++%**.#.....?.%%%%%,@@@@@@@@@@@#.%@@@@@@@@@\n@@@@@@@?.*.....+.**.*.....%.....+++%@@#+++S.%?+++.%@@@@@@@@@\n@@@@@#***......%:.**++%........++++#.#+++++.++++.S@@@@@@@@@@\n@@@@,+%.......?+++++......#....#.**+++#@@%++++.SS@@@@@@@@@@@\n@@@:+?+...?..S.......S%%%...S+++::.+++@%++++.?.#@@@@@@@@@@@@\n@@@@@@@,?...S%%*@@.?%++SS.S++.+S...?#.+++S++..@@@@@@@@@@@@@@\n@@@@@@@@@@@@@@*...?.@SS+.SS....?....#++%:+..S@@@@@@@@@@@@@@@\n@@@@@@@@@@?+S.%?#+@@@@@S...#???%%%S@+:::...@@@@@@@@@@@@@@@@@\n@@@@@@@++S....#@@@@@@@@@@@@@@@S.%...:::+#...@@@@@@@@@@@@@@@@\n@@@@#++.....S@@@@@@@@@@@@@.S..++..%?:...+?...@@@@@@@@@@@@@@@\n@@@.......?@@@@@@@@@@@@+.....+++......#.++....*@@@@@@@@@@@@@\n@@.*+...@@@@@@@@@@@@S.....?.S+..S....++...S....@@@@@@@@@@@@@\n@+*++@@@@@@@@@@@@,?........@:%.*SS?+++++..+.....%@@@@@@@@@@@\n@:+%@@@@@@@@@@@:?........?@@@#:::.+++++#...+.....#@@@@@@@@@@\n@S@@@@@@@@@@@@+.........#@@@@@@+..++++....+......S.,@@@@@@@@\n@@@@@@@@@@@@@S%##.....S@@@@@@@@@*.??.......#@%...??.#@@@@@@@\n@@@@@@@@@@@@@S%@....?S@@@@@@@@@@@@@%.?...?.@@@.S+.....@@@@@@\n@@@@@@@@@@@@@@@@S.....?@@@@@@@@@@@@@@@.%S.?@@@@+++S....@@@@@\n@@@@@@@@@@@@@@@@+......@@@@@@@@@@@@@@@@@@@@@@@@.+++S....@@@@\n@@@@@@@@@@@@@@@.%......@@@@@@@@@@@@@@@@@@@@@@@@@++++......@@\n@@@@@@@@@@@@@@.%......S@@@@@@@@@@@@@@@@@@@@@@@@@++++......@@\n@@@@@@@@@@@@@S.#.....++@@@@@@@@@@@@@@@@@@@@@@@@@..+..+....S@\n@@@@@@@@@@@.::++S.@@?+?@@@@@@@@@@@@@@@@@@@@@@@@@+...#S+?..SS\n@@@@@@@@@@@@,@,@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@.+..*++,@\n@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@.::+@@\n\nvsoch\n```\n\nYou can also use the functions on command line:\n\n```python\nfrom pokemon.skills import get_avatar\n\n# Just get the string!\navatar = get_avatar(\"vsoch\", print_screen=False)\nprint(avatar)\n\n# Remove the name at the bottom, print to screen (default)\navatar = get_avatar(\"vsoch\", include_name=False)\n```\n\n## List Pokemon\nWant a complete listing of your Pokemon choices in the database?\n\n```bash\npokemon --list\n\nSlugma\nMachop\nDruddigon\nMagby\nClawitzer\nGrowlithe\nEmpoleon\nDusknoir\nRhydon\nKrookodile\nHoppip\nSwellow\nOddish\nScrafty\nBoldore\nPancham\nBeheeyem\nHonedge\n...\nJumpluff\nRotom\nFrillish\nLapras\nClamperl\nWingull\nVespiquen\nKeldeo\nMareep\nPhantump\nMedicham\nShuckle\nLickitung\nChingling\n```\n\nYou could use this to parse through a function. Here we show a simple loop to print the name of the Pokemon, but you would be more creative!\n\n```bash\nfor gotcha in $(pokemon --list)\n    do\n    echo $gotcha\ndone\n```\n\n## Randomly select a Pokemon\n\nYou might want to just randomly get a pokemon! Do this with the `--catch` command line argument!\n\n```bash\n      pokemon --catch\n\n      @%,@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@\n      .????.@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@\n      .???????S@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@\n      :?????????#@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@\n      *?????????????*@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@\n      @???????#?????###@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@,*.??#\n      @?????,##,S???#####@@@@@@@@@@@@@@@@@@@@@@@@@@S##????????????\n      @?????*,,,,,,########@@@@@@@@@@@@@@@@@:###????????????????#@\n      @##????,,,,,,,,,#####@@@@@@@@@@@@@.######?????#?:#????????@@\n      @####?#,,,,,,,,,,,##@@@@@@@@@@@@@@#######*,,,,,*##+?????+@@@\n      @######,,,,,,,,,,,S@@@@@@@@@@@@@@#.,,,,,,,,,,,,,,:?####@@@@@\n      @######,,,,,,,,,,%@@,S.S.,@@@@@@@,,,,,,,,,,,,,,,######@@@@@@\n      @@#####,,,,,,,,.,,,,,,,,,,,,,,,*#,,,,,,,,,,,,,.#####:@@@@@@@\n      @@@@@@@@@@.#,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,######@@@@@@@@@\n      @@@@@@@@@,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,+######@@@@@@@@@@\n      @@@@@@@@%,,,,,++:,,,,,,,,,,,,,,,,,,,,,@@:.######:@@@@@@@@@@@\n      @@@@@@@:,,,:##@@@#,,,,,,,,,,,,?@S#,,,,,,@@@@@@@@@@@@@@@@@@@@\n      @@@@@@@?,,,#######,,,,,,,,,,,#.@:##,,,:?@@@@@@@@@@@@@@@@@@@@\n      @@@@@@@.,,S,??%?*,,,,,,,,,,,,####?%+,::%@@@@@@@@@@@@@@@@@@@@\n      @@@@@@@@?..*+,,,,,,*,,,,,,,,,,,+#S,::::*@@@@@@@@@@@@@@@@@@@@\n      @@@@@@@@@%..*,,,,,,,,,,,,,,,,,,,:.*...%@@@@@@@@@@@@@@@@@@@@@\n      @@@@@@@@@@.**::*::::::,,:::::::+.....@@@@@@@@@@@@@@@@@@@@@@@\n      @@@@@@@@.@@@@?:**:::*::::::::::*...@@@@@@@@@@@@@@@@@@@@@@@@@\n      @@@@@?,,,,,,,,,:,##S::::**:::S#@@@@@@@@@@@@@@@@@@@@@@@@@@@@@\n      @@@@@@@.,,,,,,:S#?##?########:#****#,@@@@@@@@@@@@@@@@@@@@@@@\n      @@@@@@@@@@,%:*%,??#,,,,:*S##**:..****:,.*@@@@@@@@@@@@@@@@@@@\n      @@@@@@@@@@@@@+,,,,,,,,,,,,,,,,,,*...*:,.,@@@@@@@@@@@@@@@@@@@\n      @@@@@@@@@@@@@+,,,,,,,,,,,,,,,,,,?@@@@@*#?@@@@@@@@@@@@@@@@@@@\n      @@@@@@@@@@@@@*,,,,,,,,,,,,,,,,,,.@#########?@@@@@@@@@@@@@@@@\n      @@@@@@@@@@@@@.*:,,,,,,,,,,,,,,:.##%,?#####????:@@@@@@@@@@@@@\n      @@@@@@@@@@@@@@?.....*******....S@@@@@@:##?????@@@@@@@@@@@@@@\n      @@@@@@@@@@@@@@S.+..********...#%@@@@@@@@@##,@@@@@@@@@@@@@@@@\n      @@@@@@@@@@@#*,,,,*.#@@@@@@@..*:,,*S@@@@@@@@@@@@@@@@@@@@@@@@@\n      @@@@@@@@@@+@,%,,,#@@@@@@@@@@,S,,,%,,:@@@@@@@@@@@@@@@@@@@@@@@\n\n      Pichu\n```\nYou can equivalently use the `--message` argument to add a custom message to your catch!\n\n```bash\n      pokemon --catch --message \"You got me!\"\n\n      @@@@@@@@@*.@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@\n      @@@@@@@@...+@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@\n      @@@@@@@@++++@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@\n      :..+,@@+.+++%@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@\n      @..++++S++++++.?...@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@\n      @@@:S.S+SSS.S%++.+++@@@@@@@@@@+.%.@@@@@@@@@@@@@@@@@@@@@@@@@@\n      @@@@:SSSSSSSSSS,@@@@@@@,:,:.SS+.....+.@@@@@@@@@@@@@@@@@@@@@@\n      @@@@,:%SS++SS.,.%,:,S,,,,+..%.........S.@@@@@@@@@@@@@@@@@@@@\n      @@@@@,:*...:,,+,.,,,,,,,*%%%++++..+++SSS+@@@@@@@@@@@@@@@@@@@\n      @@@@@@,,.....%:,,,:.:.,:.%%.SSSS++SS+%+S%,+@@@@@@@@@@@@@@@@@\n      @@@@@@@*.....S...***+,,,%..%++,?SSS.%.%%%:,.,@@@@@@@@@@@@@@@\n      @@@@@@@@,+**........,,,,....++S@,+%..#..%,,S..@@@@@@@@@@@@@@\n      @@@@@@@@@@@@@@@@*..:,,,,,%..%++S%%.%%.S%%,,*+.+@@@@@@@@@@@@@\n      @@@@@@@@@@@@@@@@S,,,,,,,,,%%%..SS..%?%%%,,,S+...@@@@@@@@@@@@\n      @@@@@@@@@@@@@@@@S.:::::::::%.%%S...%%%%:::*.....**@@@@@@@@@@\n      @@@@@@@@@@@@@@@@.%%..:::::::S%%.?%%%%%:::....**,S,,:@@@@@@@@\n      @@@@@@@@@@@@@@:::*%%%%?..*:::,.%%%%.,:*.%@@.*:,,,:,,S@....@@\n      @@@@@@@@@@@@@:,:,::*.?%%%%%%?+*%%?.?%%%%%+@@,,,,,,,.++%++@@@\n      @@@@@@@@@@@@@@*,,,,,**...*%%%%%%%%%%?++++++.@,,,,,SS+SS++@@@\n      @@@@@@@@@@@@@,,.,S,,,,:....***%%?%++++++++++.@.,,+SSSSS.S+@@\n      @@@@@@@@@@@@,,SSSS..:.%,:*..?%%??%%++++++.+S+@@@.S..%S.%.S++\n      @@@@@@@@@@@,,S.....S::*.@@@%%%%@?%%#+++++%%%?S@@@@@.%.,@@...\n      @@@@@@@@@@@:,,?.%%%::::@@@...%.@?.%.++++.+%%%%.@@@@..++@@@@@\n      @@@@@@@@@@S,.%%.:,,,,,S@@@@@.?@@+SS,S..........@@@@@,@@@@@@@\n      @@@@@@@@@@@+S...++.,,:@@@@@@@@@@@@@@@%....SSS+SS@@@@@@@@@@@@\n\n      You got me!\n```\n\nYou can also catch pokemon in your python applications. If you are going to be generating many, it is recommended to load the database once and provide it to the function, otherwise it will be loaded each time.\n\n```bash\nfrom pokemon.master import catch_em_all, get_pokemon\n\npokemons = catch_em_all()\ncatch = get_pokemon(pokemons=pokemons)\n```\n\nThe catch is a dictionary, with keys as the pokemon ID, and the value being another dictionary with various meta data (height, weight, japanese, link, ascii, etc).\n\n\n## Updating the database\n\nThe database was generated by running the script make_db.py, and you can update it by running it yourself, if at some point in the future new pokemon are added to the index.\n\n```bash\ngit clone https://github.com/vsoch/pokemon\ncd pokemon\ncd scripts\npip install -r requirements.txt\npython make_db.py\n```\n\nThen move your old database (and you can do this to keep it in case you don't want changes to persist):\n\n```bash\nmv pokemon/database dbbackup\nmv ./database pokemon/database\n```\n\nThe file pokemons.json will be saved under [pokemon/databases](pokemon/databases). Next, install as usual.\n\n```\npython setup.py install\n```\n\n## Docker\nYou can also use the [Docker image](https://hub.docker.com/r/vanessa/pokemon/),\nwhich provides the various functions and [Scientific Filesystem](https://sci-f.github.io) apps.\nThe 0.35 tag was developed with Python 2, and the 0.35 tag is Python 3 and later\n(with an updated database).\n\nWhat can I do?\n\n```bash\ndocker run vanessa/pokemon apps\n      list\n     catch\n    avatar\n```\n\nGive me my avatar!\n\n```bash\ndocker run vanessa/pokemon run avatar vsoch\n```\n\nCatch a random Pokemon\n\n```bash\ndocker run vanessa/pokemon run catch\n```\n\nWhat Pokemon can I catch?\n\n```bash\ndocker run vanessa/pokemon run list\n```\n\nCatch me Venusaur!\n\n```bash\ndocker run vanessa/pokemon run catch Venusaur\n```\n\nYou can also build the image locally:\n\n```bash\ndocker build -t vanessa/pokemon .\n```\n\n## Singularity\n\nWe can do the same with Singularity containers!\n\n\n```bash\nsudo singularity build pokemons Singularity\n```\n\nWhat can I do?\n\n```bash\n./pokemons apps\n    avatar\n     catch\n      list\n```\n\nGive me my avatar!\n\n```bash\n./pokemons run avatar vsoch\n```\n\nCatch a random Pokemon\n\n```bash\n./pokemons run catch\n```\n\nWhat Pokemons can I catch?\n\n```bash\n./pokemons list\n...\nPhantump\nTrevenant\nPumpkaboo\nGourgeist\nBergmite\nAvalugg\nNoibat\nNoivern\nXerneas\nYveltal\nZygarde\nDiancie\nHoopa\nVolcanion\n```\n\nCatch a specific Pokemon\n\n```bash\n./pokemons run catch Pikachu\n[catch] executing /bin/bash /scif/apps/catch/scif/runscript Pikachu\n@@@@@@@@@@@@@.@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@\n@@@@@@@@@@@,??@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@\n@@@@@@@@@@.###@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@\n@@@@@@@@@,##:,@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@*?@@\n@@@@@@@@@#::::@@@@@@@@@@@@@@@@@@@@@@@@@,*.???%@@@@@@@@*,,,@@\n@@@@@@@@::,,::@@@@@@@@@@@@@@@@@@%:,,:#####??,@@@@@@*,,,,,,:@\n@@@@@@@@%:,,:.@@@@@@@@@@@@@@.:::::::.#####@@@@@@@.::,,,,,::@\n@@@@@@@@%::::.,,,,:,:%@@:,:::::::::S###@@@@@@@@%,:::::,::,:%\n@@@@@@@@.S,,,,,,,,::::::::::::::::?@@@@@@@@@@?::::::::::::::\n@@@@@@@:,,,,,,,:,#.#?::::::+.,@@@@@@@@@@@@@.::::::::::::::::\n@@@@@,#:S,,:,::::*#.,:::::::*@@@@@@@@@@@@,::::::::::::::::+@\n@@@@@:%S::::::*,,:::...+.::::S@@@@@@@@@@:::::::::::::::%@@@@\n@@@@*.::::,SSSS%::::+++++:::::%@@@@@@@@:::::::::::::%@@@@@@@\n@@@@@.+:,,::S%+S::::.+++:::::::,@@@@@@@@@:::*::::S@@@@@@@@@@\n@@@@@@.S:::::.*.::::::::::::::::@@@@@@@@@,****%@@@@@@@@@@@@@\n@@@@@@@@.:::::::::::::::*:,**::::,@@@@@@@@,***@@@@@@@@@@@@@@\n@@@@,%,::::::::::::::::*.****::,:S%@@@@@@......@@@@@@@@@@@@@\n,**::::,,,,,,:::::::::::+:**:::::,::@@?.....S@@@@@@@@@@@@@@@\n%:*:,:::,,,,,,,,,,,::::::%::::::,,,::,@S..+@@@@@@@@@@@@@@@@@\n@@@@@,S%+::*,:,,::,:,,,,::::::::::::::?@@%SS?@@@@@@@@@@@@@@@\n@@@@@@@@@@@@.:,,,,:,,,,,,,:::::::::::::+SSSSS.@@@@@@@@@@@@@@\n@@@@@@@@@@@@@:,,,:::::,::::,:::::::::::*?.@@@@@@@@@@@@@@@@@@\n@@@@@@@@@@@@@+,:,:,::::::::::,,::,::::**.SS@@@@@@@@@@@@@@@@@\n@@@@@@@@@@@@@S,,:,,,,::::::::::::::::****@@@@@@@@@@@@@@@@@@@\n@@@@@@@@@@@@@@:::::::::****::::::*******S@@@@@@@@@@@@@@@@@@@\n@@@@@@@@@@@@@@@**********.%..***********@@@@@@@@@@@@@@@@@@@@\n@@@@@@@@@@@@@@@@@,?+S%@@@@@@@@@@@@......@@@@@@@@@@@@@@@@@@@@\n@@@@@@@@@@@@@@@@@@@+..*@@@@@@@@@@@@@:+**@@@@@@@@@@@@@@@@@@@@\n```\n\n\n## Issues and updates\n\nWould you like different or updated functionality?\nPlease ping me by adding an [issue](https://github.com/vsoch/pokemon/issues)!\nI did this for fun, might sneak it into a few command line applications,\nand it's pretty simple so far! I hope you have fun with it! :D\n\n\n",
        "description_content_type": "text/markdown",
        "docs_url": null,
        "download_url": "",
        "downloads": {
            "last_day": -1,
            "last_month": -1,
            "last_week": -1
        },
        "dynamic": null,
        "home_page": "https://github.com/vsoch/pokemon",
        "keywords": "pokemon,avatar,ascii,gravatar",
        "license": "LICENSE",
        "license_expression": null,
        "license_files": null,
        "maintainer": "",
        "maintainer_email": "",
        "name": "pokemon",
        "package_url": "https://pypi.org/project/pokemon/",
        "platform": null,
        "project_url": "https://pypi.org/project/pokemon/",
        "project_urls": {
            "Homepage": "https://github.com/vsoch/pokemon"
        },
        "provides_extra": null,
        "release_url": "https://pypi.org/project/pokemon/0.36/",
        "requires_dist": null,
        "requires_python": "",
        "summary": "ascii database of pokemon... in Python!",
        "version": "0.36",
        "yanked": false,
        "yanked_reason": null
    },
    "last_serial": 16452812,
    "releases": {
        "0.1": [
            {
                "comment_text": "",
                "digests": {
                    "blake2b_256": "40e7f3e80e891bb08d03ad6d0f69f6f5c0210da359de7f2064a14dedfe3833fe",
                    "md5": "cf5f8ec9193ec0b8d6fde9e0ee5db71a",
                    "sha256": "1e0abc5f79195f0677882d8117961fcdc533af7ea553ae84aa111f47a13fa2a0"
                },
                "downloads": -1,
                "filename": "pokemon-0.1.tar.gz",
                "has_sig": false,
                "md5_digest": "cf5f8ec9193ec0b8d6fde9e0ee5db71a",
                "packagetype": "sdist",
                "python_version": "source",
                "requires_python": null,
                "size": 21104373,
                "upload_time": "2016-07-25T01:05:41",
                "upload_time_iso_8601": "2016-07-25T01:05:41.197529Z",
                "url": "https://files.pythonhosted.org/packages/40/e7/f3e80e891bb08d03ad6d0f69f6f5c0210da359de7f2064a14dedfe3833fe/pokemon-0.1.tar.gz",
                "yanked": false,
                "yanked_reason": null
            }
        ],
        "0.2": [
            {
                "comment_text": "",
                "digests": {
                    "blake2b_256": "5ce0f9568f9ba22dbf618835bfc6c85a4dfb44d459fec6bad76521955ff38396",
                    "md5": "54c101cf8cbf9a0321fad874355d56c3",
                    "sha256": "1ed4ed4875ea1d2b76d4c4e556f4af22229bba10b8dabd954d68127cca4757a2"
                },
                "downloads": -1,
                "filename": "pokemon-0.2.tar.gz",
                "has_sig": false,
                "md5_digest": "54c101cf8cbf9a0321fad874355d56c3",
                "packagetype": "sdist",
                "python_version": "source",
                "requires_python": null,
                "size": 21104335,
                "upload_time": "2016-07-25T01:25:56",
                "upload_time_iso_8601": "2016-07-25T01:25:56.461624Z",
                "url": "https://files.pythonhosted.org/packages/5c/e0/f9568f9ba22dbf618835bfc6c85a4dfb44d459fec6bad76521955ff38396/pokemon-0.2.tar.gz",
                "yanked": false,
                "yanked_reason": null
            }
        ],
        "0.21": [
            {
                "comment_text": "",
                "digests": {
                    "blake2b_256": "8b0fc5652aa63c81bd400e72432115dc5156a63cf7d10113736037dad6279eb5",
                    "md5": "f22988c070544cd4968b2488359b2868",
                    "sha256": "a5835841f95dfadfce2a0e15abce91ce8405adbc96a27b63fd8c13286b63e5b7"
                },
                "downloads": -1,
                "filename": "pokemon-0.21.tar.gz",
                "has_sig": false,
                "md5_digest": "f22988c070544cd4968b2488359b2868",
                "packagetype": "sdist",
                "python_version": "source",
                "requires_python": null,
                "size": 21090122,
                "upload_time": "2017-09-14T02:49:41",
                "upload_time_iso_8601": "2017-09-14T02:49:41.200741Z",
                "url": "https://files.pythonhosted.org/packages/8b/0f/c5652aa63c81bd400e72432115dc5156a63cf7d10113736037dad6279eb5/pokemon-0.21.tar.gz",
                "yanked": false,
                "yanked_reason": null
            }
        ],
        "0.22": [
            {
                "comment_text": "",
                "digests": {
                    "blake2b_256": "dbcd58d86a5b61a566d3585695dfd5e1b64045a7b98b6fedce95365d8421d761",
                    "md5": "ffdd76135d19666fb76d70976df3767b",
                    "sha256": "d78e29baa5f04b5b8962405ca5264bddd494e1c6377c0016b295244bad3423a6"
                },
                "downloads": -1,
                "filename": "pokemon-0.22.tar.gz",
                "has_sig": false,
                "md5_digest": "ffdd76135d19666fb76d70976df3767b",
                "packagetype": "sdist",
                "python_version": "source",
                "requires_python": null,
                "size": 21090118,
                "upload_time": "2017-09-14T03:04:49",
                "upload_time_iso_8601": "2017-09-14T03:04:49.097545Z",
                "url": "https://files.pythonhosted.org/packages/db/cd/58d86a5b61a566d3585695dfd5e1b64045a7b98b6fedce95365d8421d761/pokemon-0.22.tar.gz",
                "yanked": false,
                "yanked_reason": null
            }
        ],
        "0.3": [
            {
                "comment_text": "",
                "digests": {
                    "blake2b_256": "7b4d2a0c205bfe71e8b9fcef09d210e61167008dbc3abc8148ccead7068f7049",
                    "md5": "beace9c117853737a0f52cdaa3cb225c",
                    "sha256": "07de0afebb8c16e172a27b470b51b1d3e966a6626a075055e029b89b64fbd2a3"
                },
                "downloads": -1,
                "filename": "pokemon-0.3.tar.gz",
                "has_sig": false,
                "md5_digest": "beace9c117853737a0f52cdaa3cb225c",
                "packagetype": "sdist",
                "python_version": "source",
                "requires_python": null,
                "size": 21104329,
                "upload_time": "2016-07-29T00:46:30",
                "upload_time_iso_8601": "2016-07-29T00:46:30.092413Z",
                "url": "https://files.pythonhosted.org/packages/7b/4d/2a0c205bfe71e8b9fcef09d210e61167008dbc3abc8148ccead7068f7049/pokemon-0.3.tar.gz",
                "yanked": false,
                "yanked_reason": null
            }
        ],
        "0.31": [
            {
                "comment_text": "",
                "digests": {
                    "blake2b_256": "9667c173bdd8b6ec4acff34a6b890aaa20a52bafcf12b489b32392345df13387",
                    "md5": "a07daf9e00c6da7181864ff92310d14a",
                    "sha256": "9a731f7e5b0ff7552027deaf7e0ed5be2df9f1c69fb223d0a718de0a5a0dcd6b"
                },
                "downloads": -1,
                "filename": "pokemon-0.31.tar.gz",
                "has_sig": false,
                "md5_digest": "a07daf9e00c6da7181864ff92310d14a",
                "packagetype": "sdist",
                "python_version": "source",
                "requires_python": null,
                "size": 21104416,
                "upload_time": "2016-07-29T00:48:17",
                "upload_time_iso_8601": "2016-07-29T00:48:17.362823Z",
                "url": "https://files.pythonhosted.org/packages/96/67/c173bdd8b6ec4acff34a6b890aaa20a52bafcf12b489b32392345df13387/pokemon-0.31.tar.gz",
                "yanked": false,
                "yanked_reason": null
            }
        ],
        "0.32": [
            {
                "comment_text": "",
                "digests": {
                    "blake2b_256": "bc12c30daf9ba6de2a1c4cd35d4330845631a133f3f6c09f03fb43f85e4a05bb",
                    "md5": "6f450055d57eefabbfc2643cc5abbc9e",
                    "sha256": "86f234984bf0d05560497ffadd2f712ceb6b36ce41c42c2fd7b22582a81903bd"
                },
                "downloads": -1,
                "filename": "pokemon-0.32.tar.gz",
                "has_sig": false,
                "md5_digest": "6f450055d57eefabbfc2643cc5abbc9e",
                "packagetype": "sdist",
                "python_version": "source",
                "requires_python": null,
                "size": 21104411,
                "upload_time": "2016-07-29T00:51:11",
                "upload_time_iso_8601": "2016-07-29T00:51:11.804888Z",
                "url": "https://files.pythonhosted.org/packages/bc/12/c30daf9ba6de2a1c4cd35d4330845631a133f3f6c09f03fb43f85e4a05bb/pokemon-0.32.tar.gz",
                "yanked": false,
                "yanked_reason": null
            }
        ],
        "0.33": [
            {
                "comment_text": "",
                "digests": {
                    "blake2b_256": "d63029c9689bd10bfb32bccdc28ed2da13ac195e23b36dd233fa020301e32e08",
                    "md5": "6a60877f97246456ad0afa3fff7afab1",
                    "sha256": "987ed554785fda7505b8728d2248e90ddbe012ad6cd9847dc73a1a860f949031"
                },
                "downloads": -1,
                "filename": "pokemon-0.33.tar.gz",
                "has_sig": false,
                "md5_digest": "6a60877f97246456ad0afa3fff7afab1",
                "packagetype": "sdist",
                "python_version": "source",
                "requires_python": null,
                "size": 21095109,
                "upload_time": "2018-01-21T18:36:23",
                "upload_time_iso_8601": "2018-01-21T18:36:23.720233Z",
                "url": "https://files.pythonhosted.org/packages/d6/30/29c9689bd10bfb32bccdc28ed2da13ac195e23b36dd233fa020301e32e08/pokemon-0.33.tar.gz",
                "yanked": false,
                "yanked_reason": null
            }
        ],
        "0.34": [
            {
                "comment_text": "",
                "digests": {
                    "blake2b_256": "c991b740e520872890c59d24cb60f6183068bc32750d49d8bd8ad52d6d4ac780",
                    "md5": "6cc9871e9df993c838c507354eb2a6eb",
                    "sha256": "2b99a09329a81480b03f4f2070fe606b31f48310bfc2488ef61461cf47bd11ec"
                },
                "downloads": -1,
                "filename": "pokemon-0.34.tar.gz",
                "has_sig": false,
                "md5_digest": "6cc9871e9df993c838c507354eb2a6eb",
                "packagetype": "sdist",
                "python_version": "source",
                "requires_python": null,
                "size": 21095329,
                "upload_time": "2018-01-21T19:37:33",
                "upload_time_iso_8601": "2018-01-21T19:37:33.414766Z",
                "url": "https://files.pythonhosted.org/packages/c9/91/b740e520872890c59d24cb60f6183068bc32750d49d8bd8ad52d6d4ac780/pokemon-0.34.tar.gz",
                "yanked": false,
                "yanked_reason": null
            }
        ],
        "0.35": [
            {
                "comment_text": "",
                "digests": {
                    "blake2b_256": "a353f961cebf8d15d06922b1bf48e4bb2b2b2f69626fdd602871cb604891fd3a",
                    "md5": "69fefdec524365221032246bb12c5d79",
                    "sha256": "cdbf9bcadee36376ffe1329087d614d220dc9565b1a955e40b90c87c35071889"
                },
                "downloads": -1,
                "filename": "pokemon-0.35.tar.gz",
                "has_sig": false,
                "md5_digest": "69fefdec524365221032246bb12c5d79",
                "packagetype": "sdist",
                "python_version": "source",
                "requires_python": null,
                "size": 26331571,
                "upload_time": "2020-04-11T18:14:22",
                "upload_time_iso_8601": "2020-04-11T18:14:22.378212Z",
                "url": "https://files.pythonhosted.org/packages/a3/53/f961cebf8d15d06922b1bf48e4bb2b2b2f69626fdd602871cb604891fd3a/pokemon-0.35.tar.gz",
                "yanked": false,
                "yanked_reason": null
            }
        ],
        "0.36": [
            {
                "comment_text": "",
                "digests": {
                    "blake2b_256": "b542337c5a15dcf934649f1d4d659d3cf916ba9a2b5ad128d0e70aefa3338d7a",
                    "md5": "be8c2c48394481a5b8ce67f4353f090d",
                    "sha256": "20f95b9037b197bda02269547fe90c19689df96a2383e68097a44c279a6dc1ce"
                },
                "downloads": -1,
                "filename": "pokemon-0.36.tar.gz",
                "has_sig": false,
                "md5_digest": "be8c2c48394481a5b8ce67f4353f090d",
                "packagetype": "sdist",
                "python_version": "source",
                "requires_python": null,
                "size": 29567079,
                "upload_time": "2023-01-17T04:06:36",
                "upload_time_iso_8601": "2023-01-17T04:06:36.034235Z",
                "url": "https://files.pythonhosted.org/packages/b5/42/337c5a15dcf934649f1d4d659d3cf916ba9a2b5ad128d0e70aefa3338d7a/pokemon-0.36.tar.gz",
                "yanked": false,
                "yanked_reason": null
            }
        ]
    },
    "urls": [
        {
            "comment_text": "",
            "digests": {
                "blake2b_256": "b542337c5a15dcf934649f1d4d659d3cf916ba9a2b5ad128d0e70aefa3338d7a",
                "md5": "be8c2c48394481a5b8ce67f4353f090d",
                "sha256": "20f95b9037b197bda02269547fe90c19689df96a2383e68097a44c279a6dc1ce"
            },
            "downloads": -1,
            "filename": "pokemon-0.36.tar.gz",
            "has_sig": false,
            "md5_digest": "be8c2c48394481a5b8ce67f4353f090d",
            "packagetype": "sdist",
            "python_version": "source",
            "requires_python": null,
            "size": 29567079,
            "upload_time": "2023-01-17T04:06:36",
            "upload_time_iso_8601": "2023-01-17T04:06:36.034235Z",
            "url": "https://files.pythonhosted.org/packages/b5/42/337c5a15dcf934649f1d4d659d3cf916ba9a2b5ad128d0e70aefa3338d7a/pokemon-0.36.tar.gz",
            "yanked": false,
            "yanked_reason": null
        }
    ],
    "vulnerabilities": []
}
```

### 29. Quote

**Description**:
Fetches a random quote.

**Returns:**
  - **str**: The content of a random quote followed by the author's name.

```python
from Pokemon import api

result = await api.quote()
print(result)
```

#### Expected Output

```text
The wisest men follow their own direction.

author - Euripides
```

### 30. Riddle

**Description**:
Fetches a random riddle from the Riddles API.

**Returns:**
  - **dict**: The riddle data in JSON format.

```python
from Pokemon import api

result = await api.riddle()
print(result)
```

#### Expected Output

```json
{
    "riddle": "Until I am measured, I am not known. Yet how you miss me, When I have flown.  What am I?",
    "answer": "Time"
}
```

### 31. Stackoverflow Search

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
        "view_count": 125,
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
        "view_count": 32707,
        "accepted_answer_id": 7942409,
        "answer_count": 3,
        "score": 3,
        "last_activity_date": 1577442848,
        "creation_date": 1319931614,
        "question_id": 7942384,
        "content_license": "CC BY-SA 3.0",
        "link": "https://stackoverflow.com/questions/7942384/simple-java-pokemon-fight-simulator",
        "title": "Simple Java Pokemon Fight Simulator"
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
        "view_count": 2039,
        "answer_count": 2,
        "score": 0,
        "last_activity_date": 1652730812,
        "creation_date": 1642222168,
        "last_edit_date": 1642223800,
        "question_id": 70718940,
        "content_license": "CC BY-SA 4.0",
        "link": "https://stackoverflow.com/questions/70718940/pokemon-api-request-generate-5-pok%c3%a9mon-at-a-time",
        "title": "Pokemon API request generate 5 Pok&#233;mon at a time"
    }
]
```

### 32. Upload Image

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


### 33. Wikipedia

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
    "summary": "Pok\u00e9mon is a Japanese media franchise consisting of video games, animated series and films, a trading card game, and other related media. The franchise takes place in a shared universe in which humans co-exist with creatures known as Pok\u00e9mon, a large variety of species endowed with special powers. The franchise's primary target audience is children aged 5 to 12, but it is known to attract people of all ages.\nThe franchise originated as a pair of role-playing games developed by Game Freak, from an original concept by its founder, Satoshi Tajiri. Released on the Game Boy on February 27, 1996, the games became sleeper hits and were followed by manga series, a trading card game, and anime series and films. From 1998 to 2000, Pok\u00e9mon was exported to the rest of the world, creating an unprecedented global phenomenon dubbed \"Pok\u00e9mania\". By 2002, the craze had ended, after which Pok\u00e9mon became a fixture in popular culture, with new products being released to this day. In the summer of 2016, the franchise spawned a second craze with the release of Pok\u00e9mon Go, an augmented reality game developed by Niantic. Pok\u00e9mon has since been estimated to be the world's highest-grossing media franchise and one of the best-selling video game franchises.\nPok\u00e9mon has an uncommon ownership structure. Unlike most IPs, which are owned by one company, Pok\u00e9mon is jointly owned by three: Nintendo, Game Freak, and Creatures. Game Freak develops the core series role-playing games, which are published by Nintendo exclusively for their consoles, while Creatures manages the trading card game and related merchandise, occasionally developing spin-off titles. The three companies established The Pok\u00e9mon Company (TPC) in 1998 to manage the Pok\u00e9mon property within Asia. The Pok\u00e9mon anime series and films are co-owned by Shogakukan. Since 2009, The Pok\u00e9mon Company International (TPCi), a subsidiary of TPC, has managed the franchise in all regions outside of Asia.\n\n",
    "url": "https://en.wikipedia.org/?curid=23745",
    "image_url": "https://upload.wikimedia.org/wikipedia/commons/thumb/9/98/International_Pok%C3%A9mon_logo.svg/500px-International_Pok%C3%A9mon_logo.svg.png"
}
```

### 34. Write

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
downloads/write_MuENbUyI.jpg
```


This Project is Licensed under [MIT License](https://github.com/Vivekkumar-IN/TheApi/blob/main/LICENSE)