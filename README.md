# matplotlib-cpp_with_3D_Scatter_Plot
# 3Dスキャッタプロットを備えたmatplotlib-cpp

matplotlib-cpp with 3D scatter plot is a quick hack code to add following two functions to [matplotlib-cpp](https://github.com/lava/matplotlib-cpp), which is one of the simplest C++ plotting libraries.

最も簡単なC++プロットライブラリのひとつである[matplotlib-cpp](https://github.com/lava/matplotlib-cpp)に、次の二つの関数を追加するクイックハックコードが、3Dスキャッタプットを備えたmatplotlib-cppです。

```cpp
  template<typename Numeric>
  void set_zlim(Numeric left, Numeric right);
  template<typename Numeric>
  void scatter3(const std::vector<Numeric> &x,
                const std::vector<Numeric> &y,
                const std::vector<Numeric> &z,
                const std::map<std::string, std::string> &keywords = std::map<std::string, std::string>());
```

Here is a sample code using both funcions.

両関数を用いるサンプルコードです。

```cpp
#include <random>
#include <matplotlibcpp.h>

int
main(int argc, char* argv[])
{
  std::random_device rnd;
  std::vector<double> x, y, z;
  for (int i = 0; i < 100; i++) {
    x.push_back(rnd() % 64);
    y.push_back(rnd() % 64);
    z.push_back(rnd() % 64);
  }
  matplotlibcpp::scatter3(x, y, z);
  matplotlibcpp::xlabel("X");
  matplotlibcpp::xlim(0, 64);
  matplotlibcpp::ylabel("Y");
  matplotlibcpp::ylim(0, 64);
  matplotlibcpp::set_zlabel("Z");
  matplotlibcpp::set_zlim(0, 64);
  matplotlibcpp::show();
}
```

The 3D scatter plot generated is below.

生成した3Dスキャッタプロットが下です。

![scatter plot](https://github.com/ShizSak/matplotlib-cpp_with_3D_Scatter_Plot/blob/main/matplotlib-cpp-with-3D-scatter-plot-sample.png)

If you'd like to use these functions, please patch a diff file 'matplotlibcpp.h.diff' in this repository to the original file 'matplotlibcpp.h'.

もしこれらの関数を利用されたいということであれば、もとの'matplotlibcpp.h'ファイルに対してここに置いてある差分ファイル'matplotlibcpp.h.diff'でパッチをあててください。

```
% patch -c matplotlib.cpp < matplotlibcpp.h.diff
```


Enjoy!

それでは！
