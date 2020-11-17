# Admin

운영관리 페이지

Rails version: 6.0.3.4
Ruby version: ruby 2.5.1p57 (2018-03-29 revision 63029) [x86_64-linux-gnu]

# 설치방법


아래의 명령어는 모두 RubyMine 터미널에서 진행하도록한다.

curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
curl -sL https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list

sudo apt update
sudo apt install git-core zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev software-properties-common libffi-dev nodejs yarn

git clone https://github.com/rbenv/rbenv.git ~/.rbenv
git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build

환경변수에 rbenv 를 추가해준다.
일반적으로 
~/.bashrc 파일에 최하단에
eval "$(rbenv init -)"

rbenv install 2.6.5
rbenv global 2.6.5
ruby -v

bundler 와 rails 를 설치한다.
gem install bundler
gem install rails
rbenv rehash
rails --version

sudo apt install mysql-server-5.7 mysql-client-5.7 libmysqlclient-dev
sudo apt install redis

mysql 을 서비스에 등록해줌
sudo service mysql start

데이터베이스 생성 
rake db:create


레일즈 서버 시작
rails server

https://localhost:3000 으로 이동


# 주의사항

신규 설치도중에 Webpacker configuration file not found /mnt/c/Project/untitled/config/webpacker.yml 와 같은 에러가 날경우

Gemfile.lock 파일안의 webpacker 버전을 낮추고 webpacket:install 을 재실행한다.
webpacker (4.2.1)  ->  webpacker (4.0.7)

또는 
bundle exec rails webpacker:install



