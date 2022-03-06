# matplotlib-cpp-with-3D-Scatter-Plot

matplotlib-cpp with 3D scatter plot is a quick hack code to add following two functions to matplotlib-cpp [https://github.com/lava/matplotlib-cpp], which is one of the simplest C++ plotting libraries.
```cpp
  template<typename Numeric>
  void set_zlim(Numeric left, Numeric right);
  template<typename Numeric>
  void scatter3(const std::vector<Numeric> &x,
                const std::vector<Numeric> &y,
                const std::vector<Numeric> &z,
                const std::map<std::string, std::string> &keywords = std::map<std::string, std::string>());
````

Here is a sample code using both funcions.
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
````
The scatter plot generated is below.
(matplotlib-cpp-with-3D-scatter-plot-sample.png)
