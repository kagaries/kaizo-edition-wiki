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

### equals
```java
public boolean equals(Object p_298719_) {
    if (this == p_298719_) {
        return true;
    } else {
        if (p_298719_ instanceof AdvancementHolder) {
            AdvancementHolder advancementholder = (AdvancementHolder)p_298719_;
            if (this.id.equals(advancementholder.id)) {
               return true;
            }
        }

        return false;
    }
}
```

### hashCode
```java
public int hashCode() {
    return this.id.hashCode();
}
```

### toString
```java
public String toString() {
    return this.id.toString();
}
```