3D LAMS 알고리즘
3D Local Area Multi-line Scanning (이하 3D LAMS)는 지도 내에서 두 지점 사이에 존재하는 전파환경요소(건물, 지형, 도로 등)를 단층 촬영과 같은 방식으로 3차원 공간을 추출하는 알고리즘이다. 

1. 3차원 내에서 두 위치에 대한 점을 찍고 두 점을 잇는 3차원 직선 함수를 생성.
2. 직선 위에 동일한 간격의 점 100개의 위치를 계산하여 저장.
3. 해당 점을 중심으로 하는 20x20 크기의 정사각형을 계산하고, 내부의 픽셀 값을 추출.
4. 20x20x100 크기의 3차원 배열에 해당 픽셀 값을 저장함.
5. 위 과정을 반복하여 여러 Tx-Rx에 대한 CNN 입력 이미지를 생성할 수 있음.

아래 그림에서 볼 수 있듯이 Tx와 Rx사이의 공간을 포함하는 육면체를 만들고 이를 샘플링하여 저장한다. 이때 추출되는 육면체는 크기가 20x20 인 정사각형 100개로 이루어지고, 각 정사각형은 지면에 수직이다.  

![image](https://user-images.githubusercontent.com/42092864/174632042-f554e48d-4d61-46e1-ac37-d60205d474a8.png)

				
