# matplotlib-cpp-with-3D-Scatter-Plot

matplotlib-cpp with 3D scatter plot is to add following two functions to matplotlib-cpp [https://github.com/lava/matplotlib-cpp], which is one of the simplest C++ plotting libraries.
- template<typename Numeric>
  void set_zlim(Numeric left, Numeric right)
- template<typename Numeric>
  void scatter3(const std::vector<Numeric> &x,
                const std::vector<Numeric> &y,
                const std::vector<Numeric> &z,
                const std::map<std::string, std::string> &keywords = std::map<std::string, std::string>())
