FROM ruby:latest as install
RUN gem install cf-uaac

FROM install as run
CMD [ "uaac" ]