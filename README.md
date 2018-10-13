# EasyBanner
EasyBanner Pro for Unity3d

* link: http://u3d.as/CMt
* website: http://www.u3dc.com/easybanner

# EasyBanner Pro V1.0
[TOC]

## Introduce

- **En**

  > EasyBanner Pro is developed based on Unity Ugui and is designed for a variety of scenarios that need to be banner, like scrolling pictures of web Pages. This plugin is simple to use, only need to configure the image you want to show, you can immediately see the effect, and provide a powerful parameter settings, you can fully set the effect you want, support horizontal and vertical display, support configurable multi-page display, different from the ScrollView mask principle, This plugin uses a data-driven mode, so you can set the number of pages you want to show and then use the image data to make it Infinite. Simple and easy to use interface, you can easily get Started.

- **中文**

  > EasyBanner Pro 是基于Unity UGUI 进行开发的，主要适用于各种需要Banner的场景，类似网页的滚动图片展示。本插件简单易用，只需要配置你想要展示的图片，你就能立即看到效果，并且提供强大的参数设置，你完全可以设置成你想要的效果，支持横排和竖排展示，支持可配置的多页展示，不同于scrollview的遮罩原理，本插件采用数据驱动的模式，所以，你可以设置你想展示的页面数量，然后通过图片数据让它进行无限轮播。同时我们提供简洁易用的接口，可以让你很容易就上手。


![](https://i.imgur.com/c8DesDr.png)



## API

- Property & Function

BannerView.cs

> bannerview.Loop | make the banner auto play.
>
> bannerview.Direction | set the move direction of banner.
>
> bannerview.LoopStep | The time of banner change to the next page.
>
> bannerview.ItemOffset | Offset width between item.
>
> bannerview.LerpDuration | the animation of Lerp duration.
>
> bannerview.HighLightCenter | the highlight effect for the center picture,can be override in BannerItem.cs
>
> bannerview.Axis | the axis of banner,the direction of banner.

BannerManager.cs

> bannermanager.Init(int pageCount,list<T>data) | Initialize the banner, set the banner pages and data.
>
> bannermanager.SeekToTargetItem(int index) | Seek to the target Item ,index start from zero.
>
> bannnermanger.OnNextPageClick() | select the next item.
>
> bannnermanger.OnPrePageClick() | select the pre item.
>
> bannermanager.ChangeAxisType(AxisType axis) | change the direction of banner.
>
> bannermanager.HighLightEffect(bool effect) | make hightlight effect.
>
> bannermanager.LoopBanner() | the loop fuction.
>
> bannermanager.OnTweenOver | the tween over event.

### How to use

1. Create a new scene and Canvas and EventSystem.

2. Create new Image Under the BannerRoot, you can rename it "BannerItem".and add the script "BannerItem.cs".

3. Create new Text Under the BannerItem.

4. Create new Text Under the BannerItem.

5. Create new empty gameobject under the BannerRoot ,you can rename it "BannerView",and add the stript "BannerView.cs".

6. Add new script call "Test.cs",attach to the BannerRoot.

7. Edite the code in the Test.cs :

   ```C#
   public class Test : MonoBehaviour
   {
       private int _itemCount = 3;
       private BannerView _view;
       private Banneritem _item;
       private BannerManager<Sprite> _mgr;
       public List<Sprite> Sprites;
       
       private void Start()
       {
           _view = GetComponentInChildren<BannerView>();
           _item = GetComponentInChildren<BannerItem>();
           _mgr = new BannerManager<Sprite>(_view, _item);
           _mgr.Init(_itemCount, Sprites);
       }
   }
   ```

8. add the sprite list data to the Test.cs.

9. run it.

	![](https://i.imgur.com/0IbfRzL.png)
