# Camp51.9_KioskProject_with_CiAi
html css javascript를 공부하는 동시에 파이썬을 활용하여 메이커 스페이스 키오스크를 직접 개발하는 프로젝트

## 개요
 숭실대학교 CiAi의 html 스터디와 더불어 파이썬을 활용하여 직접 개발을 통해 공부하고 또 사용한다.
 이용자들의 마스크 착용여부, 체온, 이용시간, 이용장비, 시설 등을 웹 어플리케이션으로 입력받는 키오스크 제작 및 파이어베이스 연동을 통해 문서화한다.

## ~2020/11/25
 파이썬, 텐서플로우, openCV 등 라이브러리를 활용한 마스크 감지 프로그램 실행.
 출처: https://github.com/balajisrinivas/Face-Mask-Detection
 
 아나콘다 가상환경에 프로젝트 생성 후 실행 성공.
 => detect_mask_video.py 소스파일을 아두이노와 통신하여 체온을 웹캠에 출력 및 체온, 마스크 감지 후 자동으로 로그인 사이트로 돌아가도록 추가.
 후에 html과 
 (detect_mask_video.py 일부, 마스크 감지 인공지능 실행 반복문)
 
    while True:
	# grab the frame from the threaded video stream and resize it
	# to have a maximum width of 400 pixels
	frame = vs.read()
	frame = imutils.resize(frame, width=800)

	# detect faces in the frame and determine if they are wearing a
	# face mask or not
	(locs, preds) = detect_and_predict_mask(frame, faceNet, maskNet)

	# loop over the detected face locations and their corresponding
	# locations
	for (box, pred) in zip(locs, preds):
		# unpack the bounding box and predictions
		(startX, startY, endX, endY) = box
		(mask, withoutMask) = pred

		# determine the class label and color we'll use to draw
		# the bounding box and text
		label = "Mask" if mask > withoutMask else "No Mask"
		color = (0, 255, 0) if label == "Mask" else (0, 0, 255)

		# include the probability in the label
		label = "{}: {:.2f}%".format(label, max(mask, withoutMask) * 100)

		# display the label and bounding box rectangle on the output
		# frame
		
		#if ser.readable():         #아두이노 시리얼 통신
		#	res = ser.readline()
		#	cv2.putText(frame, res.decode()[:len(res)-1], (100, 100),    #openCV에 통신값 출력
		#	cv2.FONT_HERSHEY_SIMPLEX, 0.45, color, 2)

		cv2.putText(frame, label, (startX, startY - 10),
			cv2.FONT_HERSHEY_SIMPLEX, 0.45, color, 2)
		cv2.rectangle(frame, (startX, startY), (endX, endY), color, 2)

		if mask > withoutMask:
			if max(mask, withoutMask) * 100 > 99:          #마스크를 쓴 상태에서 그 확률이 99퍼센트 이상이면 cnt 증가
				cnt+=1
				print(cnt)
				
		if max(mask, withoutMask) * 100 < 99:
			cnt = 0

	# show the output frame
	cv2.imshow("Frame", frame)
	key = cv2.waitKey(1) & 0xFF
 
	if cnt > 10:       #cnt가 10이 되면 반복문 깨고 나오기. (약 3초)
		break
  
    # do a bit of cleanup
    cv2.destroyAllWindows()    
    vs.stop()
    
    #2020/12/9
    BASE_DIR = os.path.dirname(os.path.abspath(__file__))          #반복문 종료후 loginCamp.html 실행
    webbrowser.open('file://' + os.path.join(BASE_DIR, 'htmlProject/loginCamp.html'))

## ~2020/12/9
 오븐 제작 및 간단한 로그인 페이지, 카테고리 페이지, 선택 페이지 구성 및 파이썬 프로그램 병합
 https://ovenapp.io/project/VXgARFiUcyrD0d6ypFkhgyvldzwCL3Xf#82UF4
 
## ~2020/12/17
 로그인 페이지, 회원가입 페이지, 카테고리 페이지, 선택 페이지 등 구현 
 ### 로그인 페이지
 <img width="1000" src="https://user-images.githubusercontent.com/33739448/102472006-321f0600-4099-11eb-880f-d06bfce8f716.png">
 
 ### 카테고리 페이지
 <img width="1000" src="https://user-images.githubusercontent.com/33739448/102470110-eb301100-4096-11eb-9f37-7805079293b4.png">
 
 
 

 

 
