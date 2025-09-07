# Evidencias para la unidad 4

## Código

Código para ofApp.h:

``` cpp
#pragma once
#include "ofMain.h"

struct Brush {
    float x;
    float y;
    float radio;
    float alpha;
    ofColor color;
    Brush* next;
};

struct BrushQueue {
    Brush* front;
    Brush* back;
    int size;
    int maxSize;
};

void initQueue(BrushQueue& q, int maxS);
void enqueue(BrushQueue& q, float x, float y, float r, float a, ofColor c);
void clearQueue(BrushQueue& q);
bool isEmpty(BrushQueue& q);

class ofApp : public ofBaseApp {
public:
    void setup();
    void update();
    void draw();
    void keyPressed(int key);
    void mouseMoved(int x, int y);


    BrushQueue cola;
};



```

Código para ofApp.cpp:

``` cpp
#include "ofApp.h"

void initQueue(BrushQueue& q, int maxS) {
    q.front = NULL;
    q.back = NULL;
    q.size = 0;
    q.maxSize = maxS;
}

void enqueue(BrushQueue& q, float x, float y, float r, float a, ofColor c) {
    Brush* nuevo = new Brush;
    nuevo->x = x;
    nuevo->y = y;
    nuevo->radio = r;
    nuevo->alpha = a;
    nuevo->color = c;
    nuevo->next = NULL;

    if (q.back == NULL) {
        q.front = nuevo;
        q.back = nuevo;
    }
    else {
        q.back->next = nuevo;
        q.back = nuevo;
    }

    q.size++;

    if (q.size > q.maxSize) {
        Brush* temp = q.front;
        q.front = q.front->next;
        delete temp;
        q.size--;
    }
}

void clearQueue(BrushQueue& q) {
    while (q.front != NULL) {
        Brush* temp = q.front;
        q.front = q.front->next;
        delete temp;
    }
    q.back = NULL;
    q.size = 0;
}

bool isEmpty(BrushQueue& q) {
    return q.front == NULL;
}

void ofApp::setup() {
    ofBackground(0);
    initQueue(cola, 50);
}

void ofApp::update() {}

void ofApp::draw() {
    Brush* temp = cola.front;
    while (temp != NULL) {
        ofSetColor(temp->color, temp->alpha);
        ofDrawCircle(temp->x, temp->y, temp->radio);
        temp = temp->next;
    }
}

void ofApp::mouseMoved(int x, int y) {
    enqueue(cola, x, y, ofRandom(5, 20), 200, ofColor::fromHsb(ofRandom(255), 255, 255));
}


void ofApp::keyPressed(int key) {
    if (key == 'c') { 
        clearQueue(cola);
    }
    if (key == 'a') { 
        if (cola.maxSize == 50) {
            cola.maxSize = 100;  
        }
        else {
            cola.maxSize = 50;   

           
            while (cola.size > cola.maxSize) {
                Brush* temp = cola.front;
                cola.front = cola.front->next;
                delete temp;
                cola.size--;
            }

           
            if (cola.size == 0) {
                cola.back = NULL;
            }
        }
    }
    if (key == 's') { 
        ofSaveScreen("frame_" + ofGetTimestampString() + ".png");
    }
}




```

Código para main.cpp:
``` cpp
#include "ofMain.h"
#include "ofApp.h"

//========================================================================
int main() {

	//Use ofGLFWWindowSettings for more options like multi-monitor fullscreen
	ofGLWindowSettings settings;
	settings.setSize(1024, 768);
	settings.windowMode = OF_WINDOW; //can also be OF_FULLSCREEN

	auto window = ofCreateWindow(settings);

	ofRunApp(window, make_shared<ofApp>());
	ofRunMainLoop();

}

```

## Demostración:

[Aquí está el video demostrativo de mi aplicación](https://drive.google.com/file/d/1Bt3hRYNn1udpsnhSe9YRAKo56-VGaiRC/view?usp=sharing)


