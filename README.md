# Machine-Vision


Camera Calibration
-----------
checkerboard가 찍힌 이미지들을 통해 corner를 검출 좌표로 정하여 한 뒤에 3차원 박스를 생성합니다.
checkerboard의 좌표를 기준으로 박스의 위치는 고정이며 크기를 변경할수 있습니다.

![회전1](https://user-images.githubusercontent.com/41661483/190104817-173149f3-d9b2-4c1c-8c6b-dd6893510167.png)
![회전2](https://user-images.githubusercontent.com/41661483/190104954-4d77bc1a-2ef9-4733-9fa7-07af0f10c089.png)
![크기변경](https://user-images.githubusercontent.com/41661483/190105020-b330e6af-471b-4b62-a912-c1d8e015d243.png)


Filtering
-----------
원본이미지에 image sharpening, nosie생성 등을 진행하고 average filter, gaussian filter, median filter를 적용하여 노이즈를 제거합니다.

![DOG](https://user-images.githubusercontent.com/41661483/190106550-3ff489a1-325b-4031-ba91-5c3147f8dd13.jpg)
![shapened_3img5](https://user-images.githubusercontent.com/41661483/190106824-26fc8dfb-13d2-4b81-9742-56429b0dab32.jpg)
![saltimg002](https://user-images.githubusercontent.com/41661483/190106909-b62f9030-b9d2-4896-b027-0f8e3f5287f0.jpg)
![3median_01img](https://user-images.githubusercontent.com/41661483/190108098-066a8f1e-656e-4c8d-9649-0930b5931291.jpg)


Edge & Line Fitting
-----------
Sobel Edge Detection을 이용하여 Edge를 찾고 차선을 검출하는 Line fitting을 RANSAC을 기반으로 검출하게 됩니다.

![edge](https://user-images.githubusercontent.com/41661483/190109331-845180d4-2b36-424d-9d26-76725b065567.png)
![left](https://user-images.githubusercontent.com/41661483/190109655-79c3dd4f-0b0a-479d-8f00-8c5b4de5cc3d.png)
![right](https://user-images.githubusercontent.com/41661483/190109726-c3a5b975-e6bd-4add-9f97-95a6dc86bafa.png)


SIFT & Corner Detector
-----------
코너 검출의 경우 Harris corner detector로 코너를 검출하게 되며 이외에도 SIFT 를 통해 blob을 검출합니다. 이후 blob을 통해 얻은 두 이미지들의 matching을 수행하게 됩니다.

![기본2](https://user-images.githubusercontent.com/41661483/190109952-eb314215-d2a0-4a78-9501-62244168a4d8.png)
![blob](https://user-images.githubusercontent.com/41661483/190110259-6c22d7b0-4234-4fc4-8517-da73ffdf4180.png)


Homography
-----------
SVD를 활용한 homography를 수행한 뒤에 두 영상을 합치는 과정을 수행합니다.

![tv](https://user-images.githubusercontent.com/41661483/190110587-50414f86-1c1f-4ee4-b411-be7af5b1c8ba.png)
![DOG](https://user-images.githubusercontent.com/41661483/190106550-3ff489a1-325b-4031-ba91-5c3147f8dd13.jpg)
![dtv](https://user-images.githubusercontent.com/41661483/190110766-3b90f9b6-e890-4a1d-9845-633db6bbed65.png)


이외에도 SIFT의 blob 검출하여 matching과정과 Image Stitching을 진행합니다.

![sh4](https://user-images.githubusercontent.com/41661483/190111375-7059db4c-d38b-44a9-8a24-8c19a9d68ded.jpg)
![sh3](https://user-images.githubusercontent.com/41661483/190111450-0abb1c66-a729-47c5-bb00-34046e2580c6.jpg)
![cmp](https://user-images.githubusercontent.com/41661483/190111764-d35b2b64-4872-411f-829d-58b01ee9a81b.png)
![st](https://user-images.githubusercontent.com/41661483/190112727-94c74f5d-38ee-460c-850d-b4bba154fe3e.png)

Object Detection Step by step
-----------
간단한 one-stage detector를 직접 모델을 제작합니다.

<img width="524" alt="det" src="https://user-images.githubusercontent.com/41661483/190114701-2ed344c1-e386-4633-8dd3-2386eba9aaf7.png">
