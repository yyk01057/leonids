---
layout: post
title:  "Point Test"
excerpt: "객체지향개념"
date:   2017-08-18 15:07:19
categories: [code]
comments: true
---
~~~java
class PointTest {
	public static void main(String args[]) {
		Point p = new Point();
		Point p2 = new Point(2, 2);
		Point p3 = new Point(5, 5);

		System.out.println(p.x);
		System.out.println(p.y);
		System.out.println(p);
		System.out.println(p2);
		System.out.println(p.equals(p2));

		double d = Point.getDistance(p2, p3);
		System.out.println(d);

		System.out.println(p.getDistance(p2));

		Point3D p4 = new Point3D();
		System.out.println(p4);
	}
}

// --------------------------------------------------

class Point3D extends Point {
	int z;

	Point3D() {
		this(1, 1, 1);
	}

	Point3D(int x, int y, int z) {
		super(x, y);
		this.z = z;
	}

	public String toString() {
		return super.toString() + "," + z;
	}
}

public class Point {
	int x;
	int y;

	Point() {
		// x = 1;
		// y = 1;
		this(1, 1); // Point(1,1);
	}

	Point(int a, int b) {
		x = a;
		y = b;
	}

	public double getDistance(Point p) {
		return getDistance(this, p);
	}

	public static double getDistance(Point p1, Point p2) {
		int a = p2.x - p1.x;
		int b = p2.y - p1.y;
		return Math.sqrt(a * a + b * b); // Math.sqrt(Math.pow(a,2)+Math.pow(b,2))
	}

	@Override
	public boolean equals(Object o) {
		// if(o==null) return false;
		if (!(o instanceof Point))
			return false;

		Point p = (Point) o;
		// if(this.x==p.x && this.y==p.y){
		// return true;
		// } else {
		// return false;
		// }
		return this.x == p.x && this.y == p.y;
	}

	@Override
	public String toString() {
		return x + "," + y;
	}

}
~~~
