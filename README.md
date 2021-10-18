# about-kafka

## kafka

<details open>
<summary>접기/펼치기</summary>
<div markdown="1">

    #pip install kafka-python
    
producer
    
    
    from kafka import KafkaProducer
    
    producer = KafkaProducer(
        bootstrap_servers = hostIP[:port]
    )
    
consumer
    
    from kafka import KafkaConsumer
    
    consumer = KafkaConsumer(
        topic = [topic]
        bootstrap_servers = hostIP[:port]
    )
    
    # 데이터 수신하는법 1
    consumer_records = list(consumer)
    
    # 데이터 수신하는법 2
    kafka_response = consumer.poll()

    
</div>
</details>


##### kafka 주요 옵션

    broker.id : 브로커를 구분하기 위한 ID값(key값이라고 생각하면 편할듯)
    
    delete.topic.enable : 토픽 삭제 기능을 on/off 하는 옵션
    
    default.replication.factor : 리플리켕이션팩터 옵션을 주지 않았을 경우의 기본값
    
    min.insync.replicas : 최소 리플리케이션 팩터
    
    auco.create.topics.enable : 존재하지 않는 토픽으로 퍼블리셔가 메시지를 보냈을 때 자동으로 토픽을 생성할지 설정
    
    offsets.topic.num.partitions : offsets 토픽의 파티션 수 설정
    
    offsets.topic.replication.factor : offsets 토픽의 리플리케이션 팩터
    
    compression.type : 토픽의 최종 압축 형태를 선택 gazip, snappy, lz4 등 표준 압축 포맷 지원. uncompressed는 압축하지 않음
    
    log.dirs : 로그가 저장되는 위치
    
    num.partitions : 파티션 수 옵션을 주지 않았을 때의 기본값 설정
    
    log.retention.hours : 저장된 로그의 보관주기
    
    log.segment.bytes : 저장되는 로그 파일 하나의 크기
    
    log.retention.check.interval.ms : 로그 보관 주기 체크 시간
    
    message.max.bytes : 카프카에서 허용하는 가장 큰 메시지 크기
    
    zookeeper.connect : 주키퍼 접속정보
    
    zookeeper.session.timeout.ms : 브로커와 주키퍼 사이의 최대 연결 대기 시간, 해당 시간 동안 주키퍼와 연결이 되지 않으면 타임아웃 발생
    
    unclean.leader.election.enable : ISR그룹에 포함되지 않은 마지막 리플리카를 리더로 인정 여부 설정. true(리더로 인정)/false(리더로 인정하지 않음)
    
    log.flush,.interval.ms : 메시지가 디스크로 플러시되기 전 메모리에 유지하는 시간
    
    log.fluish.interval.messages : 메시지가 디스크로 플러시되기 전 누적 메시지 수
    
