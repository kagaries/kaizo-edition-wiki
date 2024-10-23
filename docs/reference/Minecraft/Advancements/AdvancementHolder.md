# Advancement Holder

```java
public record AdvancementHolder(ResourceLocation id, Advancement value)
```

### write
```java
public void write(FriendlyByteBuf p_299066_) {
    p_299066_.writeResourceLocation(this.id);
    this.value.write(p_299066_);
}
```

### read
```java
public static AdvancementHolder read(FriendlyByteBuf p_299642_) {
    return new AdvancementHolder(p_299642_.readResourceLocation(), Advancement.read(p_299642_));
}
```