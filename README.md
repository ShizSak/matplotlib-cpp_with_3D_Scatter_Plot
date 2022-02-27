# matplotlib-cpp-with-3D-Scatter-Plot

add following two functions:
- template<typename Numeric>
  void set_zlim(Numeric left, Numeric right)
- template<typename Numeric>
  void scatter3(const std::vector<Numeric> &x,
                const std::vector<Numeric> &y,
                const std::vector<Numeric> &z,
                const std::map<std::string, std::string> &keywords = std::map<std::string, std::string>())
