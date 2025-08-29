# Redis 기초

웹개발자를 위한 Redis 기초 학습 자료입니다. 이 저장소는 템플릿에 맞춰 각 챕터를 마크다운으로 구성하고, 확인 문제와 정답/해설을 제공합니다.

## 목차

### Chapter 01 Redis 소개와 기본 개념

#### [01-1 Redis란 무엇인가](chapters/01-1_what_is_redis.md)
- 인메모리 데이터 스토어(In-memory Data Store)와 Key-Value 모델
- Redis의 특징: 단일 스레드 이벤트 루프, 성능, 단순성
- 언제 Redis를 쓰면 좋은가 (캐시, 랭킹, 세션, Pub/Sub 등)
- 3가지 키워드로 정리하는 핵심 포인트
- 확인 문제

#### [01-2 설치와 기본 사용법](chapters/01-2_installation_and_basics.md)
- 설치 방법(macOS, Linux, Docker)
- redis-server/redis-cli 기본 사용
- 기본 명령어: PING, GET/SET/DEL/EXISTS, KEY 패턴
- 5가지 키워드로 정리하는 핵심 포인트
- 확인 문제

#### [01-3 데이터 타입 개요](chapters/01-3_data_types_overview.md)
- String, List, Set, Sorted Set(ZSet), Hash
- 확장 타입: Bitmap, HyperLogLog, Geospatial, Stream
- 각 타입의 대표 명령어와 사용 예
- 5가지 키워드로 정리하는 핵심 포인트
- 확인 문제

### Chapter 02 데이터 구조와 핵심 동작 원리

#### [02-1 자료구조 심화와 사용 시나리오](chapters/02-1_data_structures_in_depth.md)
- 각 자료구조의 시간복잡도와 성능 특성
- 실제 시나리오: 랭킹, 태그, 큐, 카운팅, 세션
- 명령어 심화: MSET/MGET, HSCAN/SSCAN/ZSCAN, ZINTER/ZUNION
- 5가지 키워드로 정리하는 핵심 포인트
- 확인 문제

#### [02-2 만료와 키 스페이스 관리](chapters/02-2_expiration_and_keyspace.md)
- 만료(Expiration)와 TTL, EXPIRE/PEXPIRE/TTL/PTTL
- 키스페이스 이벤트와 알림(pubsub __keyspace@0__)
- 메모리 관리 개요와 키 설계 가이드
- 4가지 키워드로 정리하는 핵심 포인트
- 확인 문제

#### [02-3 트랜잭션, Lua, 파이프라이닝](chapters/02-3_transactions_lua_pipelining.md)
- 트랜잭션(MULTI/EXEC/DISCARD/WATCH)
- Lua 스크립트(EVAL/EVALSHA) 기본과 원자성 보장
- 파이프라이닝과 네트워크 왕복 감소
- 4가지 키워드로 정리하는 핵심 포인트
- 확인 문제

#### [02-4 메시징: Pub/Sub과 Stream](chapters/02-4_pubsub_and_streams.md)
- Pub/Sub 기초: PUBLISH/SUBSCRIBE, 패턴 구독
- Stream 개요: XADD/XREAD/XGROUP/XACK
- 이벤트 처리와 백프레셔 고려
- 4가지 키워드로 정리하는 핵심 포인트
- 확인 문제

### Chapter 03 운영 관점의 Redis

#### [03-1 메모리와 성능](chapters/03-1_memory_and_performance.md)
- 메모리 모델과 오브젝트 인코딩, lazy-free 개념
- maxmemory와 eviction 정책(allkeys-lru 등)
- 성능 측정과 모니터링(INFO, MONITOR, latency)
- 5가지 키워드로 정리하는 핵심 포인트
- 확인 문제

#### [03-2 고가용성과 확장성](chapters/03-2_availability_and_scaling.md)
- 복제(Replica)와 장애 조치(Sentinel) 개요
- Redis Cluster 개요와 샤딩 전략
- 선택 기준과 운영 팁
- 4가지 키워드로 정리하는 핵심 포인트
- 확인 문제

#### [03-3 보안과 운영 베스트 프랙티스](chapters/03-3_security_and_ops.md)
- 인증과 권한: requirepass, ACL
- 네트워크 보안과 접근 제어, 바인드/방화벽
- 로깅, 백업/복구 전략, 장애 대응 절차
- 5가지 키워드로 정리하는 핵심 포인트
- 확인 문제

### Chapter 04 실전 활용: Spring Framework와 Java

#### [04-1 Spring Cache와 Redis](chapters/04-1_spring_cache.md)
- Spring Cache Abstraction과 @Cacheable/@CacheEvict 전략
- 캐시 키 설계와 TTL 전략
- 캐시 스탬피드/스노우볼 방지 아이디어
- 5가지 키워드로 정리하는 핵심 포인트
- 확인 문제

#### [04-2 RedisTemplate과 ReactiveRedisTemplate](chapters/04-2_redis_template.md)
- 직렬화(Jackson/JSON) 설정과 타입 안전성
- 기본 CRUD, 파이프라이닝, 트랜잭션 사용 패턴
- 실습 예: 세션 스토어, 토큰 블랙리스트
- 5가지 키워드로 정리하는 핵심 포인트
- 확인 문제

#### [04-3 분산 락/레이트 리미팅/메시징](chapters/04-3_patterns_lock_rate_limit_messaging.md)
- Redisson/SET NX PX 기반 분산 락 패턴
- 레이트 리미팅 토큰 버킷 구현 개요
- Pub/Sub 및 Stream 소비자 그룹 활용 패턴
- 5가지 키워드로 정리하는 핵심 포인트
- 확인 문제

#### [04-4 구성과 운영 팁](chapters/04-4_configuration_and_ops_tips.md)
- 로컬/테스트/프로덕션 프로파일 구성
- Docker-Compose 로컬 개발, Testcontainers 통합 테스트
- 운영 모니터링, 알림, 장애 대응 플레이북
- 4가지 키워드로 정리하는 핵심 포인트
- 확인 문제

### 정답 및 해설
- [answers_and_explanations.md](answers_and_explanations.md)

### 참고
- 본 문서는 템플릿 지침을 따르며, 각 절 파일은 templates/chapter_template.md 구조를 사용합니다.

