FROM quay.io/thoth-station/s2i-thoth-ubi8-py38:v0.20.1

ENV SUMMARY="Thoth's toolchain for pytest." \
    DESCRIPTION="Thoth's toolchain for pytest."

LABEL summary="$SUMMARY" \
    description="$DESCRIPTION" \
    io.k8s.description="$DESCRIPTION" \
    io.k8s.display-name="Thoth Python 3.8-ubi8 pytest" \
    io.openshift.tags="python,python38,pytest" \
    name="thoth-station/thoth-pytest-ubi8-py38"

USER 0
COPY ./ /tmp/src-thoth-pytest
RUN  \
  pip install --upgrade pip &&\
  /usr/bin/python3 -m pip install --upgrade pip &&\
  /usr/bin/python3 -m pip install --requirement /tmp/src-thoth-pytest/requirements.txt

USER ${USERID}
