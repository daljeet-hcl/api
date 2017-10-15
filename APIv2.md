# API v2 Docs

#### The API is located at [https://api.gurbaninow.com/v2/](https://api.gurbaninow.com/v2/).

##### NOTE: This API is deprecated and is only recommended for use in old applications that need to use the old APIv2 response layout.

# Documentation

## Search

**URL**: `https://api.gurbaninow.com/v2/search/:query`  
**Example**: `https://api.gurbaninow.com/v2/search/DDrgj/?source=G&searchtype=1`


Variable|Use
:--|:--
`:query`    |The Actual Query, whatever is typed into the Search Box.<br> **INFO:** GurbaniAkhar Keyset and Unicode can be used for searching on `searchtype`: `0` and `1`. `searchtype`: `2` only supports GurbaniAkhar. **URL Encoding is Recommended**
`source`    | Sets which Source you want Shabads from:<br> **Default is All Sources**<br> `G` - Guru Granth Sahib Ji<br> `D` - Sri Dasam Granth<br> `B` - Bhai Gurdas Ji Vaaran<br> `N` - Bhai Nand Lal Ji Guzals<br> `A` - Amrit Keertan<br> `U` - Uggardanti
`searchtype`| Search Type<br> `0` - First Letter Start (Gurmukhi/Unicode) **(DEFAULT)**<br> `1` - First Letter Anywhere (Gurmukhi/Unicode)<br> `2` - Full Word/Line (Gurmukhi)<br> `3` - Full Word/Line (English)<br> `4` - Search All Words (Gurmukhi)<br> `5` - Search All Words (English)<br> `6` - Search Any Words (Gurmukhi)<br> `7` - Search Any Words (English)
`writer`    | Set Writer **(Default is All Writers)** - [WriterID List](https://github.com/GurbaniNow/gurbaninow-api/blob/master/WriterID.md)
`raag`      | Set Raag **(Default is All Raags)** - [RaagID List](https://github.com/GurbaniNow/gurbaninow-api/blob/master/RaagID.md)
`ang`       | Ang/PageNo<br>Leave Empty if Not Used<br> `1,2,3,4,....` - Specify Ang/PageNo
`results`| Set Count of Results **(DEFAULT 20, MAX 100)** <br /> In case skip is set, this will return results from the `skip` to `skip+results` results.
`skip`| Skip Records **(DEFAULT 0)** <br /> For example, if you want 20 to 30 results, set skip=20 and results=10

## Get Shabad

**URL**: `https://api.gurbaninow.com/v2/shabad/:id`  
**Example**: `https://api.gurbaninow.com/v2/shabad/3589`

Variable|Use
:--|:--
`:id`|ShabadID

## Get Line

**URL**: `https://api.gurbaninow.com/v2/line/:id`  
**Example**: `https://api.gurbaninow.com/v2/line/1`

Variable|Use
:--|:--
`:id`|Line ID  

## Get Ang

**URL**: `https://api.gurbaninow.com/v2/ang/:page` 

**URL2**: `https://api.gurbaninow.com/v2/ang/:page/:source`  

**Examples**: `https://api.gurbaninow.com/v2/ang/917`, `https://api.gurbaninow.com/v2/ang/1/D`   

Variable|Use 
:--|:--
`:ang`   | Set Ang/Paana Number (**REQUIRED**)
`:source`| Sets which Source you want Shabads from: (**OPTIONAL**) <br> `G` - Guru Granth Sahib Ji **(DEFAULT)**<br> `D` - Sri Dasam Granth<br> `B` - Bhai Gurdas Ji Vaaran<br> `N` - Bhai Nand Lal Ji Guzals<br> `A` - Amrit Keertan<br> `U` - Uggardanti

## Get Today's Hukamnama from Darbar Sahib, Amritsar

**URL**: `https://api.gurbaninow.com/v2/hukamnama/today`

##### NOTE: Hukamnama API Updates Daily at 9:00 PM Eastern Time

## Get Hukamnama Archives from Darbar Sahib, Amritsar

**URL**: `https://api.gurbaninow.com/v2/hukamnama/:year/:month/:day`

**Example**: `https://api.gurbaninow.com/v2/hukamnama/2017/1/1`

##### NOTE: Hukamnama Archives only go back up to Year 2002.

## GurbaniAkhar/Unicode Converter

**URL**: `https://api.gurbaninow.com/v2/convert/:type/:text`

Variable|Use
:--|:--
`:type`|`unicode` - GurbaniAkhar to Unicode<br> `akhar` - Unicode to GurbaniAkhar
`:text`|Text to be Converted. **URL Encoding is Recommended**
