# ATLAS螺丝枪/扭矩控制器 开放协议

## 简介

本资源文件提供了ATLAS螺丝枪/扭矩控制器的开放协议中文资料。该协议详细描述了如何通过软件与拧紧枪进行通讯，确保通讯的稳定性和准确性。

## 主要内容

1. **控制器设定开放协议可用**  
   控制器已配置为支持开放协议，允许外部软件通过网络进行通讯。

   2. **软件通过IP地址与4545默认端口号确认相应控制器**  
      软件需要通过指定的IP地址和默认端口号4545来识别并连接到相应的拧紧枪控制器。

      3. **软件发送代码MID0001请求与拧紧枪通讯通讯**
      4.    软件首先发送代码MID0001，向拧紧枪发出通讯请求。

      4. **拧紧枪反馈代码MID0002允许通讯，软件与拧紧枪连接成功**  
         拧紧枪收到MID0001后，会反馈代码MID0002，表示允许通讯，此时软件与拧紧枪连接成功。
            - **4.1 拧紧枪反馈代码MID0004表示软件代码发送错误**  
                 如果软件发送的代码有误，拧紧枪会反馈MID0004，表示代码发送错误。
                    - **4.2 拧紧枪在反馈代码MID0002后会保留15秒连线状态，超时将断开连接，反馈MID0003**  
                         连接成功后，拧紧枪会保留15秒的连线状态，如果超过15秒未收到进一步指令，连接将断开，并反馈MID0003。

                         5. **连接成功后，请每隔10秒循环发送心跳代码MID9999保持连接在线**  
                            为了保持连接在线，软件需要每隔10秒发送一次心跳代码MID9999。
                               - **5.1 心跳发送后拧紧枪会反馈MID9997已告知心跳发送成功**  
                                    拧紧枪收到心跳代码后，会反馈MID9997，表示心跳发送成功。

                                    6. **若使用开放协议选择程序，在选择程序前需要做程序上载**  
                                       在使用开放协议选择程序之前，需要先进行程序上载操作。

                                       ## 注意事项

                                       - 确保软件与拧紧枪的IP地址和端口号配置正确。
                                       - 在连接过程中，注意及时发送心跳代码以保持连接在线。
                                       - 在选择程序前，务必进行程序上载操作，以确保程序的正确执行。

                                       ## 总结

                                       本协议为ATLAS螺丝枪/扭矩控制器的开放协议提供了详细的中文资料，帮助用户更好地理解和使用该协议进行通讯操作。

                                       ## 下载链接
                                       [ATLAS螺丝枪扭矩控制器开放协议](https://pan.quark.cn/s/706926f5108b)

                                       ## 说明

                                       该仓库仅用于学习交流，请勿用于商业用途。
