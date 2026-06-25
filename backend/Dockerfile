FROM python:3.13

WORKDIR /tzApp

RUN adduser --disabled-password --comment "" user

COPY tzApp.py .

RUN chown -R user:user /tzApp

USER user

EXPOSE 8080

ENTRYPOINT ["python"]

CMD ["tzApp.py"]
