FROM mysql:5.7
LABEL maintainer "Pavel Pavlenko <region23@gmail.com>"

ENV TZ=Europe/Moscow
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
