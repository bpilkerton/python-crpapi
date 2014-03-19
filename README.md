#python-crpapi


Python library for interacting with the CRP API.

Based on python-sunlightapi, a project of Sunlight Labs (c) 2008.  
Written by James Turk <jturk@sunlightfoundation.com>.

All code is under a BSD-style license, see LICENSE for details.


##Requirements

python >= 2.4

simplejson >= 1.8 (not required with python 2.6, will use built in json module)


##Installation

To install run
```
    python setup.py install
```
which will install the bindings into python's site-packages directory.

##Usage

To initialize the api, all that is required is for it to be imported and for an
API key to be defined.

(If you do not have an API key visit http://www.opensecrets.org/api/admin/ to
register for one.)

Import modules:
```    
    >>> from crpapi import CRP, CRPApiError
```
    
And set your API key:
```    
    >>> CRP.apikey = 'yr-api-key'
```

See below for specific method usage
	

##Methods

Candidate Methods:

####candSummary
```    
>>> print CRP.candSummary.get(cid='N00007360',cycle='2014')
{u'origin': u'Center for Responsive Politics', u'next_election': u'2010', u'debt': u'0', u'last_updated': u'03/31/2009', u'cand_name': u'Pelosi, Nancy', u'cid': u'N00007360', u'spent': u'471725', u'chamber': u'H', u'state': u'CA', u'first_elected': u'1987', u'source': u'http://www.opensecrets.org/politicians/summary.php?cid=N00007360&cycle=2010', u'party': u'D', u'total': u'377304', u'cash_on_hand': u'221291', u'cycle': u'2010'}
```
		
####candContrib:
```
>>> print CRP.candContrib.get(cid='N00007360',cycle='2014')
[{u'@attributes': {u'org_name': u'Akin, Gump et al', u'total': u'18400'}}, {u'@attributes': {u'org_name': u'American Dental Assn', u'total': u'10000'}}, {u'@attributes': {u'org_name': u'Hercules Holding', u'total': u'10000'}}, {u'@attributes': {u'org_name': u'Intl Brotherhood of Electrical Workers', u'total': u'10000'}}, {u'@attributes': {u'org_name': u'Machinists/Aerospace Workers Union', u'total': u'10000'}}, {u'@attributes': {u'org_name': u'New York Life Insurance', u'total': u'10000'}}, {u'@attributes': {u'org_name': u'Operating Engineers Union', u'total': u'10000'}}, {u'@attributes': {u'org_name': u'Air Line Pilots Assn', u'total': u'5000'}}, {u'@attributes': {u'org_name': u'American Academy of Dermatology Assn', u'total': u'5000'}}, {u'@attributes': {u'org_name': u'American Fedn of St/Cnty/Munic Employees', u'total': u'5000'}}, {u'@attributes': {u'org_name': u'Amgen Inc', u'total': u'5000'}}, {u'@attributes': {u'org_name': u'Dean Foods', u'total': u'5000'}}, {u'@attributes': {u'org_name': u'Marine Engineers Beneficial Assn', u'total': u'5000'}}, {u'@attributes': {u'org_name': u'Metlife Inc', u'total': u'5000'}}, {u'@attributes': {u'org_name': u'National Beer Wholesalers Assn', u'total': u'5000'}}, {u'@attributes': {u'org_name': u'National Venture Capital Assn', u'total': u'5000'}}, {u'@attributes': {u'org_name': u'Natl Cmte to Preserve Social Security', u'total': u'5000'}}, {u'@attributes': {u'org_name': u'Sony Corp', u'total': u'5000'}}, {u'@attributes': {u'org_name': u'Transport Workers Union', u'total': u'5000'}}, {u'@attributes': {u'org_name': u'United Transportation Union', u'total': u'5000'}}]
```

####candIndustry:
```
>>> print CRP.candIndustry.get(cid='N00007360',cycle='2014')
[{u'@attributes': {u'total': u'23400', u'pacs': u'7500', u'industry_name': u'Lawyers/Law Firms', u'indivs': u'15900'}}, {u'@attributes': {u'total': u'22500', u'pacs': u'22500', u'industry_name': u'Industrial Unions', u'indivs': u'0'}}, {u'@attributes': {u'total': u'22500', u'pacs': u'22500', u'industry_name': u'Transportation Unions', u'indivs': u'0'}}, {u'@attributes': {u'total': u'20000', u'pacs': u'20000', u'industry_name': u'Health Professionals', u'indivs': u'0'}}, {u'@attributes': {u'total': u'15000', u'pacs': u'15000', u'industry_name': u'Insurance', u'indivs': u'0'}}, {u'@attributes': {u'total': u'13500', u'pacs': u'13500', u'industry_name': u'Building Trade Unions', u'indivs': u'0'}}, {u'@attributes': {u'total': u'10800', u'pacs': u'0', u'industry_name': u'Lobbyists', u'indivs': u'10800'}}, {u'@attributes': {u'total': u'10000', u'pacs': u'10000', u'industry_name': u'Hospitals/Nursing Homes', u'indivs': u'0'}}, {u'@attributes': {u'total': u'8000', u'pacs': u'8000', u'industry_name': u'TV/Movies/Music', u'indivs': u'0'}}, {u'@attributes': {u'total': u'7500', u'pacs': u'7500', u'industry_name': u'Securities & Investment', u'indivs': u'0'}}, {u'@attributes': {u'total': u'7000', u'pacs': u'7000', u'industry_name': u'Public Sector Unions', u'indivs': u'0'}}, {u'@attributes': {u'total': u'5000', u'pacs': u'5000', u'industry_name': u'Misc Issues', u'indivs': u'0'}}, {u'@attributes': {u'total': u'5000', u'pacs': u'5000', u'industry_name': u'Telecom Services & Equipment', u'indivs': u'0'}}, {u'@attributes': {u'total': u'5000', u'pacs': u'5000', u'industry_name': u'Dairy', u'indivs': u'0'}}, {u'@attributes': {u'total': u'5000', u'pacs': u'5000', u'industry_name': u'Pharmaceuticals/Health Products', u'indivs': u'0'}}, {u'@attributes': {u'total': u'5000', u'pacs': u'5000', u'industry_name': u'Beer, Wine & Liquor', u'indivs': u'0'}}, {u'@attributes': {u'total': u'3500', u'pacs': u'3500', u'industry_name': u'Real Estate', u'indivs': u'0'}}, {u'@attributes': {u'total': u'2500', u'pacs': u'2500', u'industry_name': u'Accountants', u'indivs': u'0'}}, {u'@attributes': {u'total': u'2500', u'pacs': u'2500', u'industry_name': u'Electric Utilities', u'indivs': u'0'}}, {u'@attributes': {u'total': u'2500', u'pacs': u'2500', u'industry_name': u'Construction Services', u'indivs': u'0'}}, {u'@attributes': {u'total': u'2500', u'pacs': u'2500', u'industry_name': u'Retail Sales', u'indivs': u'0'}}, {u'@attributes': {u'total': u'2500', u'pacs': u'2500', u'industry_name': u'Railroads', u'indivs': u'0'}}, {u'@attributes': {u'total': u'2500', u'pacs': u'2500', u'industry_name': u'Food & Beverage', u'indivs': u'0'}}, {u'@attributes': {u'total': u'2500', u'pacs': u'0', u'industry_name': u'Misc Business', u'indivs': u'2500'}}, {u'@attributes': {u'total': u'1000', u'pacs': u'0', u'industry_name': u'Business Services', u'indivs': u'1000'}}, {u'@attributes': {u'total': u'1000', u'pacs': u'1000', u'industry_name': u'Misc Defense', u'indivs': u'0'}}, {u'@attributes': {u'total': u'500', u'pacs': u'0', u'industry_name': u'Automotive', u'indivs': u'500'}}, {u'@attributes': {u'total': u'500', u'pacs': u'500', u'industry_name': u'Environment', u'indivs': u'0'}}]
```

####candIndByInd:
```
>>> print CRP.candIndByInd.get(cid='N00007360',cycle='2014',ind='H01')
{u'origin': u'Center for Responsive Politics', u'last_updated': u'4/27/09', u'cand_name': u'Pelosi, Nancy', u'cid': u'N00007360', u'industry': u'Health Professionals', u'pacs': u'20000', u'rank': u'0', u'indivs': u'0', u'chamber': u'H', u'state': u'California', u'source': u'http://www.opensecrets.org/industries/recips.php?Ind=H01&cycle=2010&recipdetail=H&Mem=Y&sortorder=U', u'party': u'D', u'total': u'20000', u'cycle': u'2010'}
```

####candSector:
```
>>> print CRP.candSector.get(cid='N00007360',cycle='2014')
[{u'@attributes': {u'total': u'5000', u'indivs': u'0', u'sectorid': u'A', u'pacs': u'5000', u'sector_name': u'Agribusiness'}}, {u'@attributes': {u'total': u'13000', u'indivs': u'0', u'sectorid': u'B', u'pacs': u'13000', u'sector_name': u'Communic/Electronics'}}, {u'@attributes': {u'total': u'2500', u'indivs': u'0', u'sectorid': u'C', u'pacs': u'2500', u'sector_name': u'Construction'}}, {u'@attributes': {u'total': u'1000', u'indivs': u'0', u'sectorid': u'D', u'pacs': u'1000', u'sector_name': u'Defense'}}, {u'@attributes': {u'total': u'2500', u'indivs': u'0', u'sectorid': u'E', u'pacs': u'2500', u'sector_name': u'Energy/Nat Resource'}}, {u'@attributes': {u'total': u'28500', u'indivs': u'0', u'sectorid': u'F', u'pacs': u'28500', u'sector_name': u'Finance/Insur/RealEst'}}, {u'@attributes': {u'total': u'35000', u'indivs': u'0', u'sectorid': u'H', u'pacs': u'35000', u'sector_name': u'Health'}}, {u'@attributes': {u'total': u'34200', u'indivs': u'26700', u'sectorid': u'K', u'pacs': u'7500', u'sector_name': u'Lawyers & Lobbyists'}}, {u'@attributes': {u'total': u'3000', u'indivs': u'500', u'sectorid': u'M', u'pacs': u'2500', u'sector_name': u'Transportation'}}, {u'@attributes': {u'total': u'13500', u'indivs': u'3500', u'sectorid': u'N', u'pacs': u'10000', u'sector_name': u'Misc Business'}}, {u'@attributes': {u'total': u'65500', u'indivs': u'0', u'sectorid': u'P', u'pacs': u'65500', u'sector_name': u'Labor'}}, {u'@attributes': {u'total': u'5500', u'indivs': u'0', u'sectorid': u'Q', u'pacs': u'5500', u'sector_name': u'Ideology/Single-Issue'}}]
```