# 1. 자바 실행 환경(JDK) 기반 이미지 선택 (현재 사용 중인 21 버전으로 변경)
FROM eclipse-temurin:21-jdk-jammy

# 2. 빌드된 jar 파일을 컨테이너 내부로 복사
ARG JAR_FILE=target/*.jar
COPY ${JAR_FILE} app.jar

# 3. 애플리케이션 실행
# 배포 환경(Docker)이므로 컨테이너 실행 시 'docker' 프로필을 사용하도록 설정 추가
ENTRYPOINT ["java", "-jar", "/app.jar", "--spring.profiles.active=docker"]