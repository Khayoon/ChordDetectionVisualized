 ![image](https://github.com/user-attachments/assets/79efcc03-1817-48b2-8f7b-90736b9876b5)

Elements:

![intensity vs time graph](https://github.com/user-attachments/assets/43a74f03-0fcb-4ddf-9176-140f9ea447f7)
![2D plane wound up version](https://github.com/user-attachments/assets/a62df3ed-be1e-4cb7-98fd-4169186d2a4f)
![How the winding frequency influences the center of mass](https://github.com/user-attachments/assets/61eed6d8-a89b-4891-96a8-27ae35234a5e)

Let's show how an FFT splits up a wave into its base notes, visually 

![image](https://github.com/user-attachments/assets/8c5535d1-1012-4e95-9299-377aecf1e7c4)

![image](https://github.com/user-attachments/assets/d93e9a5a-681e-40e1-9a71-dc0c22369013)

![image](https://github.com/user-attachments/assets/6774c671-20a0-4dd1-a6af-b70f98f68436)

![image](https://github.com/user-attachments/assets/c3b2ef37-08f4-43de-9ad6-5da57ae148b7)

When the winding frequency matches the signal's frequency (in this case, 3 cycles per second), all peaks align on the right and all valleys on the left. This shifts the center of mass unusually far to the right.

To visualize this, we can plot the center of mass for various winding frequencies. Since the center of mass is two-dimensional, it has an x and y coordinate. However, for now, we'll only track its x-coordinate.

For example, at a winding frequency of zero, where everything is grouped on the right, the x-coordinate of the center of mass will be relatively high.

![image](https://github.com/user-attachments/assets/e5ef4fa0-88ac-43c7-a9d2-61929a9440ef)

![image](https://github.com/user-attachments/assets/92303adb-15dc-441e-b601-35ed4ec7633e)

![image](https://github.com/user-attachments/assets/66bc8731-2571-47cf-99ac-f1c5bcf1436f)

 ![image](https://github.com/user-attachments/assets/07706680-e918-4d7b-9114-ad2b8c444fb5)

![image](https://github.com/user-attachments/assets/c39eeb4f-9148-4875-8407-ae70c57c8704)

![image](https://github.com/user-attachments/assets/b46db007-6668-4337-bbff-d19fd866501a)

what if we combine two frequncies and input them into the winder? 

![image](https://github.com/user-attachments/assets/2f805cf3-a143-4c42-9aa3-ced3f167fdda)

![image](https://github.com/user-attachments/assets/d4bd8737-d7c3-4b16-ad87-fe8eede45ea5)

Why two spikes?

![image](https://github.com/user-attachments/assets/344e43b6-3b08-43d2-8f2e-d0e8c9b43c5b)
![image](https://github.com/user-attachments/assets/085ec2b6-458f-473e-b2d8-e335ecb1f62d)
![image](https://github.com/user-attachments/assets/0a000195-07a1-4516-a212-9abef45669c2)

When you apply this transform to a pure frequency, the result is almost zero everywhere except for a distinct spike at that specific frequency (in each) pre-combine.

![image](https://github.com/user-attachments/assets/cca57b3b-51c6-4992-832d-ade1b695c682)

Think of it like this: if you combine two pure frequencies, the transform will show ** two small peaks**, each corresponding to one of the original frequencies. This means our "mathematical machine" successfully extracts the original frequencies from their mixed-up sum, much like "unmixing a bucket of paint."

There's a notion of an inverse Fourier transform that tells you which signal would have produced this as its Fourier transform. We can use this to reverse engineer a signal later.

![ inverse Fourier transform](https://github.com/user-attachments/assets/ec6e895f-679f-4d6c-bfe8-e9e7c9a7e10a)


But first. In mathematics, especially when dealing with two-dimensional concepts, it's often elegant to use the **complex plane**. In this context, the "center of mass" can be represented as a **complex number**, which inherently has both a real and an imaginary part.

![image](https://github.com/user-attachments/assets/b6c8ed02-5059-4f8b-9c70-211ea80a0c07)


The advantage of using complex numbers, instead of two coordinates, is because they are a better way to describe **winding and rotation** than real numbers. Complex numbers compactly combine magnitude and angle, allowing direct rotation and scaling through simple multiplication, which vectors lack natively. And if you think why not use a vector, complex numbers compactly combine magnitude and angle into a single entity, allowing rotation and scaling to be performed with simple multiplication, unlike vectors which require matrix operations.

A prime example is **Euler's formula**: $e^{i\theta} = \cos(\theta) + i\sin(\theta)$. This formula beautifully shows that multiplying $e$ by an imaginary number ($i$ times a real number) moves you along a circle of radius 1, counter-clockwise, starting from the positive real axis.![animation](https://github.com/user-attachments/assets/a8c0139c-b8d5-4191-be15-5a0aed034b6a)


To illustrate, consider describing a rotation at a rate of one cycle per second. You could use the expression e^(2πit), where 't' represents time. The reason for 2π is that it represents the full circumference of a unit circle.

If this feels a bit fast, you can adjust the frequency. To describe a different, perhaps slower, frequency 'f', you simply multiply 't' in the exponent by 'f'. For instance, if 'f' is 0.1 (one-tenth), the vector completes one full turn every 10 seconds. This is because 't' must increase to 10 before the entire exponent becomes 2πi.
