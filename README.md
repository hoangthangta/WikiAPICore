# WikiAPICore
This is a library used to access Wikipedia &amp; Wikidata APIs where you can get Wikipedia pages and Wikidata items. For details, please check the code.

## Dependencies
* Python >= 3.6
* spaCy >= 3.x.x
* NLTK >= 3.6.2

## Wikipedia: Examples

### Get item by Wikidata id 

Code:
```
from wiki_core import *

wiki = Wikidata()
item = wiki.get_item_by_id('Q472550', return_type = 'class')
print('item: ', vars(item)) # print class structure
print('wikidata_id: ', item.wikidata_id) # print wikidata_id
print('description: ', item.description) # print description

item = wiki.get_item_by_id('Q472550', return_type = 'dict')
print('item: ', item) # print dict
print('wikidata_id: ', item['wikidata_id']) # print wikidata_id
print('description: ', item['description']) # print description
```

Result:
```
item:  {'wikidata_id': 'Q472550', 'type': 'item', 'label': 'György Gyula Zagyva', 'description': 'Member of the National Assembly of Hungary', 'sitelink': 'György Gyula Zagyva', 'aliases': [], 'instances': [['Q5', 'human']], 'subclasses': [], 'parts': [], 'claims': [['r2', ['Q472550', 'P21', 'wikibase-item', 'Q6581097']], ['r1', ['Q472550', 'P18', 'commonsMedia', 'Zagyva Gyorgy Gyula.jpg']], ['r1', ['Q472550', 'P569', 'time', '+1976-05-18T00:00:00Z']], ['r2', ['Q472550', 'P31', 'wikibase-item', 'Q5']], ['r2', ['Q472550', 'P19', 'wikibase-item', 'Q167109']], ['r2', ['Q472550', 'P106', 'wikibase-item', 'Q82955']], ['r2', ['Q472550', 'P106', 'wikibase-item', 'Q165029']], ['r1', ['Q472550', 'P646', 'external-id', '/m/0gytjkj']], ['r2', ['Q472550', 'P27', 'wikibase-item', 'Q28']], ['r3', ['Q472550', 'P39', 'wikibase-item', 'Q17590876', ['P580', 'time', '+2010-05-14T00:00:00Z'], ['P582', 'time', '+2014-05-05T00:00:00Z'], ['P2937', 'wikibase-item', 'Q50357328'], ['P4100', 'wikibase-item', 'Q633442']]], ['r2', ['Q472550', 'P735', 'wikibase-item', 'Q942625']], ['r2', ['Q472550', 'P735', 'wikibase-item', 'Q9317185']], ['r2', ['Q472550', 'P1412', 'wikibase-item', 'Q9067']], ['r2', ['Q472550', 'P937', 'wikibase-item', 'Q1781']], ['r1', ['Q472550', 'P4966', 'external-id', 'z010']], ['r1', ['Q472550', 'P373', 'string', 'György Gyula Zagyva']], ['r1', ['Q472550', 'P6988', 'external-id', '265849']], ['r2', ['Q472550', 'P102', 'wikibase-item', 'Q633442']], ['r2', ['Q472550', 'P103', 'wikibase-item', 'Q9067']], ['r1', ['Q472550', 'P10632', 'external-id', 'Q472550']]]}
wikidata_id:  Q472550
description:  Member of the National Assembly of Hungary
```

### Get item by Wikidata title 

Code:
```
from wiki_core import *

wiki = Wikidata()
item = wiki.get_item_by_title('György Gyula Zagyva', return_type = 'class')
print('item: ', vars(item)) # print class structure
print('wikidata_id: ', item.wikidata_id) # print wikidata_id
print('description: ', item.description) # print description

item = wiki.get_item_by_title('György Gyula Zagyva', return_type = 'dict')
print('item: ', item) # print dict
print('wikidata_id: ', item['wikidata_id']) # print wikidata_id
print('description: ', item['description']) # print description
```

Result:
```
item:  {'wikidata_id': 'Q472550', 'type': 'item', 'label': 'György Gyula Zagyva', 'description': 'Member of the National Assembly of Hungary', 'sitelink': 'György Gyula Zagyva', 'aliases': [], 'instances': [['Q5', 'human']], 'subclasses': [], 'parts': [], 'claims': [['r2', ['Q472550', 'P21', 'wikibase-item', 'Q6581097']], ['r1', ['Q472550', 'P18', 'commonsMedia', 'Zagyva Gyorgy Gyula.jpg']], ['r1', ['Q472550', 'P569', 'time', '+1976-05-18T00:00:00Z']], ['r2', ['Q472550', 'P31', 'wikibase-item', 'Q5']], ['r2', ['Q472550', 'P19', 'wikibase-item', 'Q167109']], ['r2', ['Q472550', 'P106', 'wikibase-item', 'Q82955']], ['r2', ['Q472550', 'P106', 'wikibase-item', 'Q165029']], ['r1', ['Q472550', 'P646', 'external-id', '/m/0gytjkj']], ['r2', ['Q472550', 'P27', 'wikibase-item', 'Q28']], ['r3', ['Q472550', 'P39', 'wikibase-item', 'Q17590876', ['P580', 'time', '+2010-05-14T00:00:00Z'], ['P582', 'time', '+2014-05-05T00:00:00Z'], ['P2937', 'wikibase-item', 'Q50357328'], ['P4100', 'wikibase-item', 'Q633442']]], ['r2', ['Q472550', 'P735', 'wikibase-item', 'Q942625']], ['r2', ['Q472550', 'P735', 'wikibase-item', 'Q9317185']], ['r2', ['Q472550', 'P1412', 'wikibase-item', 'Q9067']], ['r2', ['Q472550', 'P937', 'wikibase-item', 'Q1781']], ['r1', ['Q472550', 'P4966', 'external-id', 'z010']], ['r1', ['Q472550', 'P373', 'string', 'György Gyula Zagyva']], ['r1', ['Q472550', 'P6988', 'external-id', '265849']], ['r2', ['Q472550', 'P102', 'wikibase-item', 'Q633442']], ['r2', ['Q472550', 'P103', 'wikibase-item', 'Q9067']], ['r1', ['Q472550', 'P10632', 'external-id', 'Q472550']]]}
item:  Q472550
item:  Member of the National Assembly of Hungary
```

### Search by Wikidata

Code:
```
from wiki_core import *
wiki = Wikidata()

result = wiki.search_wikidata('science', search_type = 'property', limit = 5) # seach by property ([https://www.wikidata.org/wiki/Wikidata:List_of_properties](https://www.wikidata.org/wiki/Wikidata:Glossary#Property))
print('result: ', result)

result = wiki.search_wikidata('science', search_type = 'item', limit = 5) # search by Wikidata identifier (item, https://www.wikidata.org/wiki/Wikidata:Glossary#Item)
print('result: ', result)
```

Result:
```
result:  [{'wikidata_id': 'P2579', 'title': 'Property:P2579', 'label': 'studied by', 'datatype': 'wikibase-item', 'object_type': 'property'}, {'wikidata_id': 'P10376', 'title': 'Property:P10376', 'label': 'ScienceDirect topic ID', 'datatype': 'external-id', 'object_type': 'property'}, {'wikidata_id': 'P8694', 'title': 'Property:P8694', 'label': 'Science Museum Group ID', 'datatype': 'external-id', 'object_type': 'property'}, {'wikidata_id': 'P9268', 'title': 'Property:P9268', 'label': 'Science Magazine author ID', 'datatype': 'external-id', 'object_type': 'property'}, {'wikidata_id': 'P4389', 'title': 'Property:P4389', 'label': 'Science Museum people ID', 'datatype': 'external-id', 'object_type': 'property'}]

result:  [{'wikidata_id': 'Q336', 'title': 'Q336', 'label': 'science', 'datatype': 'wikibase-item', 'object_type': 'item'}, {'wikidata_id': 'Q192864', 'title': 'Q192864', 'label': 'Science', 'datatype': 'wikibase-item', 'object_type': 'item'}, {'wikidata_id': 'Q845056', 'title': 'Q845056', 'label': 'Science', 'datatype': 'wikibase-item', 'object_type': 'item'}, {'wikidata_id': 'Q24925', 'title': 'Q24925', 'label': 'science fiction', 'datatype': 'wikibase-item', 'object_type': 'item'}, {'wikidata_id': 'Q21198', 'title': 'Q21198', 'label': 'computer science', 'datatype': 'wikibase-item', 'object_type': 'item'}]
```

### Get triples
Code:
```
from wiki_core import *
wiki = Wikidata()
triples = wiki.get_triple('science', level = 2)
print('triples: ', triples)
```

Result:
```
triples:  [['science', 'instance_of', 'academic discipline'], ['science', 'instance_of', 'activity'], ['science', 'subclass_of', 'knowledge system'], ['academic discipline', 'instance_of', 'classification system of knowledge'], ['academic discipline', 'subclass_of', 'specialty'], ['activity', 'subclass_of', 'series'], ['activity', 'subclass_of', 'occurrence'], ['knowledge system', 'subclass_of', 'system'], ['knowledge system', 'subclass_of', 'set'], ['knowledge system', 'subclass_of', 'knowledge'], ['system', 'instance_of', 'type of object'], ['system', 'subclass_of', 'collective entity'], ['set', 'subclass_of', 'collective entity'], ['knowledge', 'instance_of', 'philosophical concept'], ['knowledge', 'instance_of', 'mental state'], ['knowledge', 'subclass_of', 'memory']]
```

## Wikidata: Examples

###

# Contact
* Email: tahoangthang@gmail.com
