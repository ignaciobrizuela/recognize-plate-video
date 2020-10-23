# Recognize plate in video

_This is a simple script to capture images from an IP camera through RTSP protocol and then look for plates in the frames, converting them to text and then comparing them with an specific plate number_

## Let´s get started 🚀

_Before to start coding we need to install some libraries.._

### Pre-requirements 📋

_It´s highly recommended to work in Linux, this will do things easier and with less problems._

_First of all, we need to install (unless you have it)._

```
- python 2.7
- pip
```

_Then, install openalpr and opencv._

```
https://github.com/sunfic/openalpr-opencv4
```

### Proccess 🔧

_**convert2pnm** is necessary to convert our frame to the correct format for the openalpr algorithm._

_Once you connect your IP camera to your neetwork you can run **AdVanced IP Scanner** to find the address._

```
192.168.88.172
```

_There are different ways to initialize a video object in openCV._

_What we need it's the RTSP protocol._

_In this example a HIKVISION camera was used._

```
v = cv2.VideoCapture('rtsp://192.168.88.172:554/user=admin&password=123456&channel=1&stream=0.sdp?')
```

_Look at that we use the IP address that Advanced IP Scanner gave us **192.168.88.172** and then we add **:554** that it's the rtsp port._

_There are 2 important things here._

```
user=admin
password=123456
```

_You must change them for your camera parameters._

## Test ⚙️

_Instead of a video, this example uses an image._

![auto](https://user-images.githubusercontent.com/40641262/97018996-2ba36080-1526-11eb-8514-c392242da3ac.jpg)

_Afert execute the code you will notice that there are a lot of information in the shell._

```
reulst['results']
```

_But the relevant data that we're looking for is the **plate number**._

```
for r in result['results']:
  ...
  if r['plate'] == 'AB123CD':
```

- r['plate'] - contains the number plate of the image (if there is a plate of course).

_You could change 'AB123CD' to the desired plate number._

## Thanks 🎁

- That's it

- I hope this will help you 🤓

## Author ✒️

---

⌨️[IgnacioBrizuela](https://github.com/ignaciobrizuela)
