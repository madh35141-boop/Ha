#include <iostream>
using namespace std;

class ElectronicDevice {
protected:
    string brand;   
    int power;     

public:
    ElectronicDevice(string b, int p) : brand(b), power(p) {}

    void turnOn() {
        cout << "تم تشغيل الجهاز الإلكتروني." << endl;
    }

    void turnOff() {
        cout << "تم إيقاف تشغيل الجهاز الإلكتروني." << endl;
    }
    void showInfo() {
        cout << "العلامة التجارية: " << brand << endl;
        cout << "استهلاك الطاقة: " << power << " واط" << endl;
    }
};
class SmartPhone : public ElectronicDevice {
private:
    int cameraMP;   
    int storage;    

public:
    SmartPhone(string b, int p, int cam, int st)
        : ElectronicDevice(b, p), cameraMP(cam), storage(st) {}

    void takePhoto() {
        cout << "التقاط صورة بدقة " << cameraMP << " ميغابكسل." << endl;
    }

    void showPhoneInfo(){
        showInfo();
        cout << "دقة الكاميرا: " << cameraMP << " MP" << endl;
        cout << "سعة التخزين: " << storage << " GB" << endl;
    }
};

int main() {
    SmartPhone phone("Apple", 20, 48, 128);

    cout << "=== معلومات الهاتف الذكي ===" << endl;
    phone.showPhoneInfo();

    cout << "\n=== تجربة وظائف الهاتف ===" << endl;
    phone.turnOn();     
    phone.takePhoto(); 
    phone.turnOff();    
    return 0;
}
