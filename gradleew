#!/bin/bash
DIR="$( cd "$( dirname "${BASH_SOURCE[0]}" )" && pwd )"
GRADLE_WRAPPER_PROPERTIES_FILE="$DIR/gradle/wrapper/gradle-wrapper.properties"
if ! test -f "$GRADLE_WRAPPER_PROPERTIES_FILE"; then
  echo "Could not find gradle-wrapper.properties. Please run gradle wrapper first."
  exit 1
fi
GRADLE_WRAPPER_URL=$(grep distributionUrl $GRADLE_WRAPPER_PROPERTIES_FILE | sed -e 's/.*=\(.*\)/\1/')
curl -s $GRADLE_WRAPPER_URL -o gradle-wrapper.jar
chmod +x gradle-wrapper.jar
java -jar gradle-wrapper.jar "$@"
