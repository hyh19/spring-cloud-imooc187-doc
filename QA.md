# 常见问题汇总

## 1. 无法下载SpringBoot 2.0.0.M3和SpringCloud Finchley.M2

解决方法：
+ 在pom.xml文件里加上如下代码(可参考[product的pom.xml](https://gitlab-demo.com/SpringCloud_Sell/product/blob/master/pom.xml))：

```
<repositories>
		<repository>
			<id>spring-snapshots</id>
			<name>Spring Snapshots</name>
			<url>https://repo.spring.io/snapshot</url>
			<snapshots>
				<enabled>true</enabled>
			</snapshots>
		</repository>
		<repository>
			<id>spring-milestones</id>
			<name>Spring Milestones</name>
			<url>https://repo.spring.io/milestone</url>
			<snapshots>
				<enabled>false</enabled>
			</snapshots>
		</repository>
	</repositories>

	<pluginRepositories>
		<pluginRepository>
			<id>spring-snapshots</id>
			<name>Spring Snapshots</name>
			<url>https://repo.spring.io/snapshot</url>
			<snapshots>
				<enabled>true</enabled>
			</snapshots>
		</pluginRepository>
		<pluginRepository>
			<id>spring-milestones</id>
			<name>Spring Milestones</name>
			<url>https://repo.spring.io/milestone</url>
			<snapshots>
				<enabled>false</enabled>
			</snapshots>
		</pluginRepository>
	</pluginRepositories>
```

+ 若在自己配置了国内maven库镜像后无法下载以上版本，则请将镜像注释掉，用maven默认的中央仓库下载（如果觉得太慢，就用科学上网）