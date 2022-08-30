# MCMOT_ByteTrack-ReID-Jetson-Nano
Để chạy model MCMOT+ReID trên Jetson : 
1. Cài đặt hệ điều hành ubuntu cho jetson 
2. Cài đặt môi trường biên dịch python 
3. Cài đặt CUDA hỗ trợ GPU 
4. Cài đặt Pytorch , TensoRTflow , và các thư viện trong file"requirements.txt"
5. Cài đặt thư viện hỗ trợ  xử lý dữ liệu có dạng như COCO : pip3 install 'git+https://github.com/cocodataset/cocoapi.git#subdirectory=PythonAPI'
6. Cài đặt cython và cython_bbox :
pip3 install cython
pip3 install cython_bbox
6. Tải model tại : https://github.com/CaptainEven/MCMOT-ByteTrack
7. Câu lệnh để chạy demo trên GPU: 
python3 "đường dẫn file demo_track_GPU.py"  video --path "đường dẫn video"-f " đường dẫn đến file yolox_tiny_track_c5_darknet.py"-c "đường dẫn đến file latest_ckpt.pth.tar" --fp16 --fuse --save_result " đường dẫn lưu video kết quả" &> log.txt

VD: 
python3 /content/MCMOT-ByteTrack/tools/demo_mcmot.py --path /content/gdrive/MyDrive/test.mp4 -f /content/MCMOT-ByteTrack/exps/example/mot/yolox_tiny_track_c5_darknet.py -c /content/gdrive/MyDrive/latest_ckpt.pth.tar --fp16 --fuse --save_result /content/MCMOT-ByteTrack/output &> log.txt

8. Câu lệnh chạy demo trên cpu : 
python3 "đường dẫn file demo_track_CPU.py"  video --path "đường dẫn video"-f " đường dẫn đến file yolox_tiny_track_c5_darknet.py"-c "đường dẫn đến file latest_ckpt.pth.tar" --fp32 --fuse --save_result " đường dẫn lưu video kết quả" &> log.txt

Tải weight tại  : https://drive.google.com/file/d/1CFiRkLrvuWacX6NqkFDBbcMBNCrEoz6h/view?usp=sharing
Thay thế các file
