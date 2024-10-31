# BlockUtil

```java
public class BlockUtil
```

## FoundRectangle.getLargestRectangleAround
```java
public static BlockUtil.FoundRectangle getLargestRectangleAround(BlockPos p_124335_, Direction.Axis p_124336_, int p_124337_, Direction.Axis p_124338_, int p_124339_, Predicate<BlockPos> p_124340_) {
    BlockPos.MutableBlockPos blockpos$mutableblockpos = p_124335_.mutable();
    Direction direction = Direction.get(Direction.AxisDirection.NEGATIVE, p_124336_);
    Direction direction1 = direction.getOpposite();
    Direction direction2 = Direction.get(Direction.AxisDirection.NEGATIVE, p_124338_);
    Direction direction3 = direction2.getOpposite();
    int i = getLimit(p_124340_, blockpos$mutableblockpos.set(p_124335_), direction, p_124337_);
    int j = getLimit(p_124340_, blockpos$mutableblockpos.set(p_124335_), direction1, p_124337_);
    int k = i;
    BlockUtil.IntBounds[] ablockutil$intbounds = new BlockUtil.IntBounds[i + 1 + j];
    ablockutil$intbounds[i] = new BlockUtil.IntBounds(getLimit(p_124340_, blockpos$mutableblockpos.set(p_124335_), direction2, p_124339_), getLimit(p_124340_, blockpos$mutableblockpos.set(p_124335_), direction3, p_124339_));
    int l = ablockutil$intbounds[i].min;

    for(int i1 = 1; i1 <= i; ++i1) {
        BlockUtil.IntBounds blockutil$intbounds = ablockutil$intbounds[k - (i1 - 1)];
        ablockutil$intbounds[k - i1] = new BlockUtil.IntBounds(getLimit(p_124340_, blockpos$mutableblockpos.set(p_124335_).move(direction, i1), direction2, blockutil$intbounds.min), getLimit(p_124340_, blockpos$mutableblockpos.set(p_124335_).move(direction, i1), direction3, blockutil$intbounds.max));
    }

    for(int l2 = 1; l2 <= j; ++l2) {
        BlockUtil.IntBounds blockutil$intbounds2 = ablockutil$intbounds[k + l2 - 1];
        ablockutil$intbounds[k + l2] = new BlockUtil.IntBounds(getLimit(p_124340_, blockpos$mutableblockpos.set(p_124335_).move(direction1, l2), direction2, blockutil$intbounds2.min), getLimit(p_124340_, blockpos$mutableblockpos.set(p_124335_).move(direction1, l2), direction3, blockutil$intbounds2.max));
    }

    int i3 = 0;
    int j3 = 0;
    int j1 = 0;
    int k1 = 0;
    int[] aint = new int[ablockutil$intbounds.length];

    for(int l1 = l; l1 >= 0; --l1) {
        for(int i2 = 0; i2 < ablockutil$intbounds.length; ++i2) {
            BlockUtil.IntBounds blockutil$intbounds1 = ablockutil$intbounds[i2];
            int j2 = l - blockutil$intbounds1.min;
            int k2 = l + blockutil$intbounds1.max;
            aint[i2] = l1 >= j2 && l1 <= k2 ? k2 + 1 - l1 : 0;
        }

        Pair<BlockUtil.IntBounds, Integer> pair = getMaxRectangleLocation(aint);
        BlockUtil.IntBounds blockutil$intbounds3 = pair.getFirst();
        int k3 = 1 + blockutil$intbounds3.max - blockutil$intbounds3.min;
        int l3 = pair.getSecond();
        if (k3 * l3 > j1 * k1) {
            i3 = blockutil$intbounds3.min;
            j3 = l1;
            j1 = k3;
            k1 = l3;
        }
    }

    return new BlockUtil.FoundRectangle(p_124335_.relative(p_124336_, i3 - k).relative(p_124338_, j3 - l), j1, k1);
}
```