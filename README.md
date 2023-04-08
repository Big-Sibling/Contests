# ICTMentoringProject
ICT 멘토링 프로젝트를 위한 데이터분석&amp;모델링 코드들 


## base-dataset 함수에 대한 설명
#### Selenium_.py 
- get_directory() : 파일 생성, 변수로는 파일명을 받습니다.
  - name : 새로 생성할 파일명. 이미 해당 이름의 파일이 있으면 생성하지 않고 넘어감
- get_google_image() : 구글에서 이미지 다운로드 변수로는 검색명, 받을 데이터의 개수를 받습니다.
  - query : 검색할 내용 Ex. 엑소수호 이미지를 불러오고싶으면 엑소수호를 입력하기
  - max_count : 최대 몇장을 크롤링할 건지
- get_naver_image() : 이건 네이버에서 이미지 다운로드 함수입니다. 인자는 구글과 똑같아요.

#### mycv2
- newImread() : cv2의 imread와 받는 변수는 똑같아요. cv2가 한글경로를 인식하지 못하는 문제를 해결하기 위해 만든 함수입니다. 
  - 하단의 imgCrop안의 ImageCrop()함수 안에서 쓰여서 직접적으로 쓸 일은 없을 거에요!
  - Ex. image = mycv2.newImread(os.path.join(file_path, file_list[i])) 
- newImwrite() : cv2의 imwrite와 받는 변수는 똑같아요. cv2가 한글경로를 인식하지 못하는 문제를 해결하기 위해 numpy를 써서 인코딩 해주는 함수입니다.

#### imgCrop 
- ImageCrop() : 얼굴만 인식해서 크롭해주는 함수입니다. openCV의 pretrained된 haarcascade를 썼어요 frontal_face 함수를 써서 정면만 인식하고 측면이나 너무 작은 얼굴 등은 드롭하게끔 했습니다. 
  - 주의 : 같이 올린 xml이 파일 내부에 있어야합니다!
  - file_path : 크롭하기 전 원본사진이 있는 경로를 넣어주세요 마지막에 '/'를 붙여주세요 
    - Ex. C:/Users/hop09/Desktop/ToyProject/
  - xml_path : 같이 올린 xml이 존재하는 파일경로를 넣어주세요 이것도 마지막에 '/'를 붙여주세요
  - new_img_name : 얼굴위주로 크롭한 사진의 이름을 정해주세요. 
