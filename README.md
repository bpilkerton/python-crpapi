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
{u'origin': u'Center for Responsive Politics', u'next_election': u'2014', u'debt': u'0', u'last_updated': u'12/31/2013', u'cand_name': u'Pelosi, Nancy', u'cid': u'N00007360', u'spent': u'1304840.24', u'chamber': u'H', u'state': u'CA', u'first_elected': u'1987', u'source': u'http://www.opensecrets.org/politicians/summary.php?cid=N00007360&cycle=2014', u'party': u'D', u'total': u'1294719.87', u'cash_on_hand': u'439206.96', u'cycle':u'2014'}
```
		
####candContrib:
```
>>> print CRP.candContrib.get(cid='N00007360',cycle='2014')
{u'origin': u'Center for Responsive Politics', u'next_election': u'2014', u'debt': u'0', u'last_updated': u'12/31/2013', u'cand_name': u'Pelosi, Nancy', u'cid': u'N00007360', u'spent': u'1304840.24', u'chamber': u'H', u'state': u'CA', u'first_elected': u'1987', u'source': u'http://www.opensecrets.org/politicians/summary.php?cid=N00007360&cycle=2014', u'party': u'D', u'total': u'1294719.87', u'cash_on_hand': u'439206.96', u'cycle':u'2014'}>>> print CRP.candContrib.get(cid='N00007360',cycle='2014')[{u'@attributes': {u'org_name': u'Certain Software Inc', u'total': u'10400'}}, {u'@attributes': {u'org_name': u'Chartwell Hotels', u'total': u'10400'}}, {u'@attributes': {u'org_name': u'Jewish Community Federation', u'total': u'10400'}}, {u'@attributes': {u'org_name': u'Marcus & Millichap', u'total': u'10400'}}, {u'@attributes': {u'org_name': u'Stanford University', u'total': u'10400'}}, {u'@attributes': {u'org_name': u'Facebook Inc', u'total': u'10200'}}, {u'@attributes': {u'org_name': u'American Assn for Justice', u'total': u'10000'}},{u'@attributes': {u'org_name': u'American Health Care Assn', u'total': u'10000'}}, {u'@attributes': {u'org_name': u'Boeing Co', u'total': u'10000'}},{u'@attributes': {u'org_name': u'Francisco Partners', u'total': u'10000'}}]
```

####candIndustry:
```
>>> print CRP.candIndustry.get(cid='N00007360',cycle='2014')
[{u'@attributes': {u'total': u'74750', u'industry_code': u'H01', u'industry_name': u'Health Professionals', u'pacs': u'70500', u'indivs': u'4250'}}, {u'@attributes':{u'total': u'62500', u'industry_code': u'K01', u'industry_name': u'Lawyers/Law Firms', u'pacs': u'21500', u'indivs': u'41000'}}, {u'@attributes':{u'total': u'51200', u'industry_code': u'F10', u'industry_name': u'Real Estate', u'pacs': u'27500', u'indivs': u'23700'}}, {u'@attributes':{u'total':u'50600', u'industry_code': u'B12', u'industry_name': u'Computers/Internet', u'pacs': u'25000', u'indivs': u'25600'}}, {u'@attributes':{u'total': u'45000', u'industry_code': u'P01', u'industry_name': u'Building Trade Unions', u'pacs': u'45000', u'indivs':u'0'}}, {u'@attributes':{u'total': u'39250', u'industry_code': u'F07', u'industry_name': u'Securities & Investment', u'pacs': u'16000', u'indivs': u'23250'}},{u'@attributes': {u'total': u'39000', u'industry_code': u'H02', u'industry_name': u'Hospitals/Nursing Homes', u'pacs': u'35000', u'indivs': u'4000'}},{u'@attributes': {u'total': u'38000', u'industry_code': u'P04', u'industry_name': u'Public Sector Unions', u'pacs': u'38000', u'indivs': u'0'}},{u'@attributes': {u'total': u'37900', u'industry_code': u'B02', u'industry_name': u'TV/Movies/Music', u'pacs': u'14500', u'indivs': u'23400'}},{u'@attributes': {u'total': u'35800', u'industry_code': u'F13', u'industry_name': u'Misc Finance', u'pacs': u'0', u'indivs': u'35800'}}]
```

####candIndByInd:
```
>>> print CRP.candIndByInd.get(cid='N00007360',cycle='2014',ind='H01')
{u'origin': u'Center for Responsive Politics', u'last_updated': u'2/18/14', u'cand_name': u'Pelosi, Nancy', u'cid': u'N00007360', u'industry': u'Health Professionals', u'pacs': u'70500', u'rank': u'36', u'indivs': u'4250', u'chamber': u'H', u'state': u'California', u'source': uhttp://www.opensecrets.org/industries/recips.php?Ind=H01&cycle=2014&recipdetail=H&Mem=Y&sortorder=U', u'party': u'D', u'total': u'74750', u'cycle': u'2014'}
```

####candSector:
```
>>> print CRP.candSector.get(cid='N00007360',cycle='2014')
[{u'@attributes': {u'total': u'11000', u'indivs': u'0', u'sectorid': u'A', u'pacs': u'11000', u'sector_name': u'Agribusiness'}}, {u'@attributes': {u'total': u'104900', u'indivs': u'59400', u'sectorid': u'B', u'pacs': u'45500', u'sector_name': u'Communic/Electronics'}}, {u'@attributes': {u'total': u'15800', u'indivs': u'9800', u'sectorid': u'C', u'pacs': u'6000', u'sector_name': u'Construction'}},{u'@attributes': {u'total': u'24000', u'indivs': u'0', u'sectorid': u'D', u'pacs':u'24000', u'sector_name': u'Defense'}}, {u'@attributes': {u'total': u'5500',u'indivs': u'0', u'sectorid': u'E', u'pacs': u'5500', u'sector_name': u'Energy/Nat Resource'}}, {u'@attributes': {u'total': u'154500', u'indivs': u'84000', u'sectorid': u'F', u'pacs': u'70500', u'sector_name':u'Finance/Insur/RealEst'}}, {u'@attributes': {u'total': u'126500', u'indivs': u'8500', u'sectorid': u'H', u'pacs': u'118000', u'sector_name':u'Health'}}, {u'@attributes': {u'total': u'73600', u'indivs': u'52100', u'sectorid': u'K', u'pacs': u'21500', u'sector_name': u'Lawyers &Lobbyists'}},{u'@attributes': {u'total': u'21000', u'indivs': u'0', u'sectorid': u'M', u'pacs': u'21000', u'sector_name': u'Transportation'}}, {u'@attributes':{u'total': u'82900', u'indivs': u'67400', u'sectorid': u'N', u'pacs': u'15500', u'sector_name': u'Misc Business'}}, {u'@attributes': {u'total': u'165500', u'indivs': u'0', u'sectorid': u'P', u'pacs': u'165500', u'sector_name': u'Labor'}}, {u'@attributes': {u'total': u'67030', u'indivs': u'36680', u'sectorid': u'Q', u'pacs': u'30350', u'sector_name': u'Ideology/Single-Issue'}}, {u'@attributes': {u'total': u'65850', u'indivs': u'63850', u'sectorid': u'W',u'pacs': u'2000', u'sector_name': u'Other'}}]
```