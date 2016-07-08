# UICollectionView-
UICollectionView自定义布局

实例中包含两种布局UICollectionViewLineLayout继承自UICollectionViewFlowLayout和UICollectionViewCircleLayout继承自UICollectionViewLayout,通过点击控制器view来切换两种不同的布局方式

###继承自UICollectionViewFlowLayout和UICollectionViewLayout的区别
    UICollectionViewFlowLayout：
        layoutAttributesForElementsInRect方法中调用[super layoutAttributesForElementsInRect:rect]能得到rect范围内的UICollectionViewLayoutAttributes属性数组
        实现shouldInvalidateLayoutForBoundsChange方法。当collectionView显示的区域发生变化时调用1.prepareLayout  2.layoutAttributesForElementsInRect刷新界面
        当collectionView需要切换布局样式为自己的时候，不需要实现layoutAttributesForItemAtIndexPath方法
    UICollectionViewLayout：
        layoutAttributesForElementsInRect方法中调用[super layoutAttributesForElementsInRect:rect]得不到item的属性数组，一切属性需要自己设置
        不需要实现shouldInvalidateLayoutForBoundsChange方法。且prepareLayout只调用一次，layoutAttributesForElementsInRect调用多次
        当collectionView需要切换布局样式为自己的时候，需要实现layoutAttributesForItemAtIndexPath方法.返回indexPath位置对应的cell的局部属性UICollectionViewLayoutAttributes
        需要实现collectionViewContentSize方法，实现滚动
        
        
 ![image](https://github.com/linchaosheng/UICollectionView-/blob/master/uicollectionview.gif)
