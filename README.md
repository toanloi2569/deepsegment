```[python]
from pyvi import ViTokenizer
from deepsegment2 import DeepSegment

segmenter = DeepSegment(checkpoint_path='/output7/checkpoint',params_path='/output7/params', utils_path='/output7/utils')
p = "Theo dõi , đánh giá kết quả làm việc của các nhân viên công ty Tư vấn và hỗ trợ khách hàng có nhu cầu đăng tin rao vặt bất động sản lên website Các công việc khác theo yêu cầu"

p = ViTokenizer.tokenize(p).replace("_"," ").replace("-", "").replace("+", "")
list_sentences = segmenter.segment_long(p.strip(),10)
print(list_sentences)
```
