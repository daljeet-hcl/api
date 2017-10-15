# GurbaniNow API [![badge](https://img.shields.io/badge/Powered%20By-GurbaniNow-blue.svg)](https://github.com/GurbaniNow)

⚡️ 🙏 Fast and Powerful JSON API used by [GurbaniNow Search](https://gurbaninow.com) and many other projects.

GurbaniNow API utilizes the [CloudFlare CDN](https://www.cloudflare.com/cdn/) to bring Gurbani to developers all over the [world](https://www.cloudflare.com/network/) at lightning fast speeds!

If you need help, have an issue, or would like to request an feature, please submit it [here](https://github.com/GurbaniNow/gurbaninow-api/issues/new)!

**NOTE:** This API is in Development and not Public. The following is documentation for APIv3 which may or may not be changed in the development process.

#### The API is located at https://api.gurbaninow.com.

![alt text](https://i.imgur.com/3jmzSNa.jpg)

### Used By
[GurbaniNow](https://gurbaninow.com) | [AKJ.Org](https://akj.org/dailyhukam.php) | [/r/sikh Hukamnama Bot](https://www.reddit.com/user/Hukumnama_Bot) | [Nitnem App](https://play.google.com/store/apps/details?id=parwinder.singh.sikhism)
:--|:--|:--|:--

# Documentation

## Search

**URL**: `https://api.gurbaninow.com/v3/search/:query`  
**Example**: `https://api.gurbaninow.com/v3/search/DDrgj/?source=G&searchtype=1`


Variable|Use
:--|:--
`:query`    |The Actual Query, whatever is typed into the Search Box.<br> **INFO:** GurbaniAkhar Keyset and Unicode can be used for searching on `searchtype`: `0` and `1`. `searchtype`: `2` only supports GurbaniAkhar. **URL Encoding is Recommended**
`source`    | Sets Source **(Default is All Sources)** - [SourceID List](https://github.com/GurbaniNow/gurbaninow-api/blob/master/SourceID.md)
`searchtype`| Search Type<br> `0` - First Letter Start (Gurmukhi/Unicode) **(DEFAULT)**<br> `1` - First Letter Anywhere (Gurmukhi/Unicode)<br> `2` - Full Word/Line (Gurmukhi)<br> `3` - Full Word/Line (English)<br> `4` - Search All Words (Gurmukhi)<br> `5` - Search All Words (English)<br> `6` - Search Any Words (Gurmukhi)<br> `7` - Search Any Words (English)
`writer`    | Set Writer **(Default is All Writers)** - [WriterID List](https://github.com/GurbaniNow/gurbaninow-api/blob/master/WriterID.md)
`raag`      | Set Raag **(Default is All Raags)** - [RaagID List](https://github.com/GurbaniNow/gurbaninow-api/blob/master/RaagID.md)
`ang`       | Ang/PageNo<br>Leave Empty if Not Used<br> `1,2,3,4,....` - Specify Ang/PageNo
`results`| Set Count of Results **(DEFAULT 20, MAX 100)** <br /> In case skip is set, this will return results from the `skip` to `skip+results` results.
`skip`| Skip Records **(DEFAULT 0)** <br /> For example, if you want 20 to 30 results, set skip=20 and results=10

## Get Shabad

**URL**: `https://api.gurbaninow.com/v3/shabad/:id`  
**Example**: `https://api.gurbaninow.com/v3/shabad/3589`

Variable|Use
:--|:--
`:id`|ShabadID

## Get Shabad Using STTM2 Shabad ID's

**URL**: `https://api.gurbaninow.com/v3/sttmshabad/:id`  
**Example**: `https://api.gurbaninow.com/v3/sttmshabad/3589`

Variable|Use
:--|:--
`:id`|STTM2 ShabadID

**NOTE:** For Legacy Apps and Websites that need access to Shabads using old SikhiToTheMax II ShabadID's (ex. SikhNet)

## Get Line

**URL**: `https://api.gurbaninow.com/v3/line/:id`  
**Example**: `https://api.gurbaninow.com/v3/line/1`

Variable|Use
:--|:--
`:id`|Line ID  

## Get Ang

**URL**: `https://api.gurbaninow.com/v3/ang/:page` 

**URL2**: `https://api.gurbaninow.com/v3/ang/:page/:source`  

**Examples**: `https://api.gurbaninow.com/v3/ang/917`, `https://api.gurbaninow.com/v3/ang/1/D`   

Variable|Use 
:--|:--
`:ang`   | Set Ang/Paana Number (**REQUIRED**)
`:source`| **[OPTIONAL]** Set Source **(Default is Guru Granth Sahib Ji - `G`)** - [SourceID List](https://github.com/GurbaniNow/gurbaninow-api/blob/master/SourceID.md)

## Gutka / Precompiled Baanis

**URL**: `https://api.gurbaninow.com/v3/baani/:baani` 

**Examples**: `https://api.gurbaninow.com/v3/baani/japjisahib` 

Variable|Use 
:--|:--
`:baani` | [Baani List](https://github.com/GurbaniNow/gurbaninow-api/blob/master/BaaniList.md)

## Amrit Keertan Pothi

### Get List of Topics

**URL**: `https://api.gurbaninow.com/v3/amritkeertan`

### Get List of Sub Topics from Main Topic

**URL**: `https://api.gurbaninow.com/v3/amritkeertan/:topicid`

Variable|Use
:--|:--
`:topicid`|Topic ID

### Get List of Shabads from Sub Topic

**URL**: `https://api.gurbaninow.com/v3/amritkeertan/:topicid/:subtopicid`

Variable|Use
:--|:--
`:topicid`|Topic ID
`:subtopicid`|Sub Topic ID

## Get Today's Hukamnama from Darbar Sahib, Amritsar

**URL**: `https://api.gurbaninow.com/v3/hukamnama/today`

##### NOTE: Hukamnama API Updates Daily at 9:00 PM Eastern Time

## Get Hukamnama Archives from Darbar Sahib, Amritsar

**URL**: `https://api.gurbaninow.com/v3/hukamnama/:year/:month/:day`

**Example**: `https://api.gurbaninow.com/v3/hukamnama/2017/1/1`

##### NOTE: Hukamnama Archives only go back up to Year 2002.

## GurbaniAkhar/Unicode Converter

**URL**: `https://api.gurbaninow.com/v3/convert/:type/:text`

Variable|Use
:--|:--
`:type`|`unicode` - GurbaniAkhar to Unicode<br> `akhar` - Unicode to GurbaniAkhar
`:text`|Text to be Converted. **URL Encoding is Recommended**


# Licence

```
GurbaniNow API Copyright (C) 2015-2017 GurbaniNow Dev Team. All Rights Reserved.

Any Data recieved by any means from the GurbaniNow API is licensed under  
Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International.

You should have received a copy of the license along with this  
work.  If not, see <https://creativecommons.org/licenses/by-nc-nd/4.0/>.

THE GURBANINOW API IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR  
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,  
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE  
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER  
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,  
OUT OF OR IN CONNECTION WITH THE GURBANINOW API OR THE USE OR OTHER DEALINGS IN  
THE GURBANINOW API.

April 14, 2017
Subject To Change
```
