FROM registry.cn-beijing.aliyuncs.com/alphesh-soft/openjdk:17-jdk
WORKDIR /data
# 定义应用的用户和用户组,为pod的安全配置准备
ARG APP_UID=1001
ARG APP_GID=1001
COPY app .
# 创建应用用户和用户组，给应用目录设置权限
RUN groupadd -r appgroup --gid=${APP_GID} && \
    useradd -r --uid=${APP_UID} --gid=${APP_GID} --shell=/bin/false appuser && \
    chown -R ${APP_UID}:${APP_GID} /data