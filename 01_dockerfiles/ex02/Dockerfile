FROM ruby

RUN apt-get update -y && apt-get install -y build-essential libpq-dev nodejs sqlite3

ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD EXPOSE 3000
ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed

# 1. create ft-rails dir
# 2. move this Docker file there
# 3. copy original docker file from Subject in ex02
# 4. clone ruby app in app from https://bitbucket.org/railstutorial/sample_app_4th_ed.git 

# Build
# docker build -t ft-rails:on-build .
# docker build -t ex02 .
# Run
# docker run -it --rm -p 3000:3000 ex02
