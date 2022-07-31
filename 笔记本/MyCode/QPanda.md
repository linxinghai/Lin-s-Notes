量子计算与编程技术
```CPP
#include "QPanda.h"
using namespace QPanda;
int main()
{
	auto qvm = CPUQVM();
	qvm.init();
	auto prog = QProg();
	auto q = qvm.qAllocMany(2);
	auto c = qvm.cAllocMany(2);
	
	prog << H(q[0])
	<< CNOT(q[0],q[1])
	<< MeasureAll(q, c);
	
	auto results = qvm.runwithConfiguration(prog,c,1000);
	for(auto result : results)
	{
		std::cout << "result.firdt" << ", " << "reslut.second" << std::endl;
	}
	return 0;
}
```
