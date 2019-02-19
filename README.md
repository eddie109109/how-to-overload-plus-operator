# how-to-overload-plus-operator


class Point {

private:
    int x,y;

public:
    Point(int x = 0, int y = 0);
    int getX() const;
    int getY() const;
    void setX(int x);
    void setY(int y);
    void print() const;
    const Point operator+(const Point & rhs) const;
};


Point::Point(int x, int y)
:x(x),y(y) {}

int Point::getX() const {
    return x;
}

int Point::getY() const {
    return y;
}

void Point::setX(int x) {
    this->x = x;
}

void Point::setY(int y) {
    this->y = y;
}

void Point::print() const {
    cout << "the value for x is " << this->x << " and y is " << this->y << endl;
}

const Point Point::operator+(const Point & rhs) const {
    return Point(x + rhs.x, y + rhs.y);
}


int main() {
    Point p1;
    Point p2;
    p1.setX(10);
    p1.setY(20);
    p2.setX(29);
    p2.setY(30);
    Point p3;
    p3 = p2 + p2;
    p3.print();
    // I get x = 39 and y = 50


}
