# Blaze3D

```java
@OnlyIn(Dist.CLIENT)
public class Blaze3D
```

## process

Goes unused within 1.20.2

```java
public static void process(RenderPipeline p_166119_, float p_166120_) {
    ConcurrentLinkedQueue<RenderCall> concurrentlinkedqueue = p_166119_.getRecordingQueue();
}
```

## render

Goes unused within 1.20.2

```java
public static void render(RenderPipeline p_166122_, float p_166123_) {
    ConcurrentLinkedQueue<RenderCall> concurrentlinkedqueue = p_166122_.getProcessedQueue();
}
```

## youJustLostTheGame

Used with debug crash trigger while holding control

```java
public static void youJustLostTheGame() {
    MemoryUtil.memSet(0L, 0, 1L);
}
```

## getTime

Used to get the current running time

```java
public static double getTime() {
    return GLFW.glfwGetTime();
}
```