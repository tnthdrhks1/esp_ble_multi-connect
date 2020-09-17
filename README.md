 bool isNotify) {
    uint32_t data0 = pData[0] | (pData[1] << 8) | (pData[2] << 16) | (pData[3] << 24);
    /*
    Serial.print("Notify callback for characteristic ");
    Serial.print(pBLERemoteCharacteristic->getUUID().toString().c_str());
    Serial.print(" of data length ");
    Serial.println(length);
    */
    Serial.print("data: ");
    Serial.println(data0);
    a++;
    Serial.print("a = ");
    Serial.println(a);

    if(a == 20){
      esp_sleep_enable_timer_wakeup(1 * 1000000);
      esp_deep_sleep_start();
      }
}

이부분이 핵심

여기서 client에 파이어베이스 코드를 합치려 했으나 스캐치 메모리 부족으로 하지 못함

그래서 client를 라즈베리파이로 변경
