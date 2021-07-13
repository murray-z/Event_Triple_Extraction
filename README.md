# Event_Triple_Extraction
采用LTP抽取事件三元组


```
from triple_extraction_ltp import TripleExtraction

content1 = '李克强总理今天来我家了,我感到非常荣幸'
content2 = ''' 以色列国防军20日对加沙地带实施轰炸，造成3名巴勒斯坦武装人员死亡。此外，巴勒斯坦人与以色列士兵当天在加沙地带与以交界地区发生冲突，一名巴勒斯坦人被打死。当天的冲突还造成210名巴勒斯坦人受伤。当天，数千名巴勒斯坦人在加沙地带边境地区继续“回归大游行”抗议活动。部分示威者燃烧轮胎，并向以军投掷石块、燃烧瓶等，驻守边境的以军士兵向示威人群发射催泪瓦斯并开枪射击。'''

extractor = TripleExtraction()
for text in [content1, content2]:
    print(text)
    res = extractor.triples_main(text)
    print(res)
    
# [['李克强总理', '来', '我家'], ['我', '感到', '非常荣幸']]
# [['以色列国防军', '实施', '轰炸'], ['冲突', '发生', '巴勒斯坦人与以色列士兵'], ['当天冲突', '造成', '210名巴勒斯坦人受伤'], ['数千名巴勒斯坦人', '继续', '回归大游行抗议活动'], ['部分示威者', '燃烧', '轮胎'], ['部分示威者', '投掷', '石块燃烧瓶'], ['，', '驻守', '边境'], ['驻守边境以军士兵', '发射', '催泪瓦斯']]

```

- 根据https://github.com/liuhuanyong/EventTriplesExtraction改编，替换pyltp为ltp;
- pyltp太难安装了..........
