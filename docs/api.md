# Protocol Documentation11
<a name="top"></a>

## Table of Contents

- [sogage/v1/common.proto](#sogage_v1_common-proto)
    - [ApiError](#sogage-v1-ApiError)
    - [ApiError.DetailsEntry](#sogage-v1-ApiError-DetailsEntry)
    - [CurrencyReward](#sogage-v1-CurrencyReward)
    - [Deck](#sogage-v1-Deck)
    - [DeckUnit](#sogage-v1-DeckUnit)
    - [DeviceInfo](#sogage-v1-DeviceInfo)
    - [DeviceInfo.ExtraEntry](#sogage-v1-DeviceInfo-ExtraEntry)
    - [ItemReward](#sogage-v1-ItemReward)
    - [Pagination](#sogage-v1-Pagination)
    - [PlayerProfile](#sogage-v1-PlayerProfile)
    - [PlayerProfile.CurrenciesEntry](#sogage-v1-PlayerProfile-CurrenciesEntry)
    - [ResponseMeta](#sogage-v1-ResponseMeta)
    - [Reward](#sogage-v1-Reward)
  
    - [CurrencyType](#sogage-v1-CurrencyType)
    - [ErrorCode](#sogage-v1-ErrorCode)
    - [ItemRarity](#sogage-v1-ItemRarity)
    - [Platform](#sogage-v1-Platform)
    - [StoreType](#sogage-v1-StoreType)
  
- [sogage/v1/game_api.proto](#sogage_v1_game_api-proto)
    - [GameService](#sogage-v1-GameService)
  
    - [AppleIdentity](#sogage-v1-AppleIdentity)
    - [CurrencyPayment](#sogage-v1-CurrencyPayment)
    - [DrawGachaRequest](#sogage-v1-DrawGachaRequest)
    - [DrawGachaResponse](#sogage-v1-DrawGachaResponse)
    - [DrawGachaResponse.CurrencyBalancesEntry](#sogage-v1-DrawGachaResponse-CurrencyBalancesEntry)
    - [GachaItem](#sogage-v1-GachaItem)
    - [GachaResult](#sogage-v1-GachaResult)
    - [GachaUnit](#sogage-v1-GachaUnit)
    - [GetHomeRequest](#sogage-v1-GetHomeRequest)
    - [GetHomeResponse](#sogage-v1-GetHomeResponse)
    - [GetHomeResponse.CountersEntry](#sogage-v1-GetHomeResponse-CountersEntry)
    - [GuestIdentity](#sogage-v1-GuestIdentity)
    - [LoginRequest](#sogage-v1-LoginRequest)
    - [LoginRequest.ClientMetaEntry](#sogage-v1-LoginRequest-ClientMetaEntry)
    - [LoginResponse](#sogage-v1-LoginResponse)
    - [NewsBanner](#sogage-v1-NewsBanner)
    - [NewsBanner.ExtrasEntry](#sogage-v1-NewsBanner-ExtrasEntry)
    - [OAuthIdentity](#sogage-v1-OAuthIdentity)
    - [PaidCurrencyPayment](#sogage-v1-PaidCurrencyPayment)
    - [PresentBoxItem](#sogage-v1-PresentBoxItem)
    - [PurchaseProductRequest](#sogage-v1-PurchaseProductRequest)
    - [PurchaseProductResponse](#sogage-v1-PurchaseProductResponse)
    - [PurchaseProductResponse.InventoryDeltaEntry](#sogage-v1-PurchaseProductResponse-InventoryDeltaEntry)
    - [StartQuestRequest](#sogage-v1-StartQuestRequest)
    - [StartQuestRequest.ClientParamsEntry](#sogage-v1-StartQuestRequest-ClientParamsEntry)
    - [StartQuestResponse](#sogage-v1-StartQuestResponse)
    - [StoreReceiptPayment](#sogage-v1-StoreReceiptPayment)
    - [TicketPayment](#sogage-v1-TicketPayment)
  
- [Scalar Value Types](#scalar-value-types)



<a name="sogage_v1_common-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## sogage/v1/common.proto





<a name="sogage-v1-ApiError"></a>

### ApiError



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| code | [ErrorCode](#sogage-v1-ErrorCode) |  |  |
| message | [string](#string) |  |  |
| details | [ApiError.DetailsEntry](#sogage-v1-ApiError-DetailsEntry) | repeated | 例: {"field": "gacha_id", "reason": "not_found"} |






<a name="sogage-v1-ApiError-DetailsEntry"></a>

### ApiError.DetailsEntry



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| key | [string](#string) |  |  |
| value | [string](#string) |  |  |






<a name="sogage-v1-CurrencyReward"></a>

### CurrencyReward



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| type | [CurrencyType](#sogage-v1-CurrencyType) |  |  |
| amount | [int64](#int64) |  |  |






<a name="sogage-v1-Deck"></a>

### Deck



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| deck_id | [string](#string) |  |  |
| units | [DeckUnit](#sogage-v1-DeckUnit) | repeated |  |






<a name="sogage-v1-DeckUnit"></a>

### DeckUnit



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| unit_id | [string](#string) |  |  |
| position | [int32](#int32) |  |  |
| level | [int32](#int32) |  |  |
| rarity | [ItemRarity](#sogage-v1-ItemRarity) |  |  |
| equipped_item_ids | [string](#string) | repeated |  |






<a name="sogage-v1-DeviceInfo"></a>

### DeviceInfo



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| platform | [Platform](#sogage-v1-Platform) |  |  |
| device_model | [string](#string) |  |  |
| os_version | [string](#string) |  |  |
| app_version | [string](#string) |  |  |
| extra | [DeviceInfo.ExtraEntry](#sogage-v1-DeviceInfo-ExtraEntry) | repeated |  |






<a name="sogage-v1-DeviceInfo-ExtraEntry"></a>

### DeviceInfo.ExtraEntry



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| key | [string](#string) |  |  |
| value | [string](#string) |  |  |






<a name="sogage-v1-ItemReward"></a>

### ItemReward



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| item_id | [string](#string) |  |  |
| amount | [int64](#int64) |  |  |
| rarity | [ItemRarity](#sogage-v1-ItemRarity) |  |  |
| display_name | [google.protobuf.StringValue](#google-protobuf-StringValue) |  | 表示用（存在しない場合もある） |






<a name="sogage-v1-Pagination"></a>

### Pagination



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| page_size | [int32](#int32) |  |  |
| page_token | [string](#string) |  |  |






<a name="sogage-v1-PlayerProfile"></a>

### PlayerProfile



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| player_id | [string](#string) |  |  |
| name | [string](#string) |  |  |
| level | [int32](#int32) |  |  |
| exp | [int32](#int32) |  |  |
| stamina | [int32](#int32) |  |  |
| stamina_max | [int32](#int32) |  |  |
| created_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  |  |
| currencies | [PlayerProfile.CurrenciesEntry](#sogage-v1-PlayerProfile-CurrenciesEntry) | repeated | key: 任意（"gold", "gems_free" など） |
| unlocked_feature_flags | [string](#string) | repeated |  |






<a name="sogage-v1-PlayerProfile-CurrenciesEntry"></a>

### PlayerProfile.CurrenciesEntry



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| key | [string](#string) |  |  |
| value | [int64](#int64) |  |  |






<a name="sogage-v1-ResponseMeta"></a>

### ResponseMeta



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| request_id | [string](#string) |  |  |
| server_time | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  |  |
| error | [ApiError](#sogage-v1-ApiError) |  |  |






<a name="sogage-v1-Reward"></a>

### Reward
付与アイテムの例。


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| currency | [CurrencyReward](#sogage-v1-CurrencyReward) |  |  |
| item | [ItemReward](#sogage-v1-ItemReward) |  |  |





 <!-- end messages -->


<a name="sogage-v1-CurrencyType"></a>

### CurrencyType
代表的な通貨種別。

| Name | Number | Description |
| ---- | ------ | ----------- |
| CURRENCY_TYPE_UNSPECIFIED | 0 |  |
| CURRENCY_TYPE_GOLD | 1 |  |
| CURRENCY_TYPE_GEMS_FREE | 2 |  |
| CURRENCY_TYPE_GEMS_PAID | 3 |  |
| CURRENCY_TYPE_STAMINA | 4 |  |



<a name="sogage-v1-ErrorCode"></a>

### ErrorCode
共通のエラーコード。

| Name | Number | Description |
| ---- | ------ | ----------- |
| ERROR_CODE_UNSPECIFIED | 0 |  |
| ERROR_CODE_UNKNOWN | 1 |  |
| ERROR_CODE_INVALID_ARGUMENT | 2 |  |
| ERROR_CODE_UNAUTHENTICATED | 3 |  |
| ERROR_CODE_FORBIDDEN | 4 |  |
| ERROR_CODE_NOT_FOUND | 5 |  |
| ERROR_CODE_CONFLICT | 6 |  |
| ERROR_CODE_RATE_LIMITED | 7 |  |
| ERROR_CODE_INSUFFICIENT_FUNDS | 8 |  |
| ERROR_CODE_MAINTENANCE | 9 |  |



<a name="sogage-v1-ItemRarity"></a>

### ItemRarity
レアリティ例。

| Name | Number | Description |
| ---- | ------ | ----------- |
| ITEM_RARITY_UNSPECIFIED | 0 |  |
| ITEM_RARITY_N | 1 |  |
| ITEM_RARITY_R | 2 |  |
| ITEM_RARITY_SR | 3 |  |
| ITEM_RARITY_SSR | 4 |  |
| ITEM_RARITY_UR | 5 |  |



<a name="sogage-v1-Platform"></a>

### Platform
クライアントプラットフォーム。

| Name | Number | Description |
| ---- | ------ | ----------- |
| PLATFORM_UNSPECIFIED | 0 |  |
| PLATFORM_IOS | 1 |  |
| PLATFORM_ANDROID | 2 |  |
| PLATFORM_WEB | 3 |  |



<a name="sogage-v1-StoreType"></a>

### StoreType
課金ストア種別。

| Name | Number | Description |
| ---- | ------ | ----------- |
| STORE_TYPE_UNSPECIFIED | 0 |  |
| STORE_TYPE_APP_STORE | 1 |  |
| STORE_TYPE_GOOGLE_PLAY | 2 |  |
| STORE_TYPE_DMM | 3 |  |


 <!-- end enums -->

 <!-- end HasExtensions -->



<a name="sogage_v1_game_api-proto"></a>
<p align="right"><a href="#top">Top</a></p>

## sogage/v1/game_api.proto




<a name="sogage-v1-GameService"></a>

### GameService
ソシャゲでよくあるAPIを "5本" まとめたサンプル。

| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| Login | [LoginRequest](#sogage-v1-LoginRequest) | [LoginResponse](#sogage-v1-LoginResponse) |  |
| GetHome | [GetHomeRequest](#sogage-v1-GetHomeRequest) | [GetHomeResponse](#sogage-v1-GetHomeResponse) |  |
| DrawGacha | [DrawGachaRequest](#sogage-v1-DrawGachaRequest) | [DrawGachaResponse](#sogage-v1-DrawGachaResponse) |  |
| StartQuest | [StartQuestRequest](#sogage-v1-StartQuestRequest) | [StartQuestResponse](#sogage-v1-StartQuestResponse) |  |
| PurchaseProduct | [PurchaseProductRequest](#sogage-v1-PurchaseProductRequest) | [PurchaseProductResponse](#sogage-v1-PurchaseProductResponse) |  |





<a name="sogage-v1-AppleIdentity"></a>

### AppleIdentity



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| identity_token | [string](#string) |  |  |
| nonce | [string](#string) |  |  |






<a name="sogage-v1-CurrencyPayment"></a>

### CurrencyPayment



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| currency_type | [CurrencyType](#sogage-v1-CurrencyType) |  |  |
| amount | [int64](#int64) |  |  |






<a name="sogage-v1-DrawGachaRequest"></a>

### DrawGachaRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| access_token | [string](#string) |  |  |
| gacha_id | [string](#string) |  |  |
| count | [int32](#int32) |  |  |
| paid | [PaidCurrencyPayment](#sogage-v1-PaidCurrencyPayment) |  |  |
| ticket | [TicketPayment](#sogage-v1-TicketPayment) |  |  |
| skip_animation | [google.protobuf.BoolValue](#google-protobuf-BoolValue) |  |  |






<a name="sogage-v1-DrawGachaResponse"></a>

### DrawGachaResponse



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| meta | [ResponseMeta](#sogage-v1-ResponseMeta) |  |  |
| results | [GachaResult](#sogage-v1-GachaResult) | repeated |  |
| currency_balances | [DrawGachaResponse.CurrencyBalancesEntry](#sogage-v1-DrawGachaResponse-CurrencyBalancesEntry) | repeated | key: CurrencyType の数値（例: 2=GEMS_FREE） |






<a name="sogage-v1-DrawGachaResponse-CurrencyBalancesEntry"></a>

### DrawGachaResponse.CurrencyBalancesEntry



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| key | [int32](#int32) |  |  |
| value | [int64](#int64) |  |  |






<a name="sogage-v1-GachaItem"></a>

### GachaItem



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| item_id | [string](#string) |  |  |
| amount | [int64](#int64) |  |  |






<a name="sogage-v1-GachaResult"></a>

### GachaResult



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| result_id | [string](#string) |  |  |
| rarity | [ItemRarity](#sogage-v1-ItemRarity) |  |  |
| unit | [GachaUnit](#sogage-v1-GachaUnit) |  |  |
| item | [GachaItem](#sogage-v1-GachaItem) |  |  |






<a name="sogage-v1-GachaUnit"></a>

### GachaUnit



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| unit_id | [string](#string) |  |  |
| level | [int32](#int32) |  |  |






<a name="sogage-v1-GetHomeRequest"></a>

### GetHomeRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| access_token | [string](#string) |  |  |
| client_revision | [google.protobuf.Int64Value](#google-protobuf-Int64Value) |  | クライアントが保持するリビジョン（差分更新の例） |
| include_sections | [string](#string) | repeated | お知らせ/プレゼント等を分割取得する想定。 |
| pagination | [Pagination](#sogage-v1-Pagination) |  |  |






<a name="sogage-v1-GetHomeResponse"></a>

### GetHomeResponse



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| meta | [ResponseMeta](#sogage-v1-ResponseMeta) |  |  |
| profile | [PlayerProfile](#sogage-v1-PlayerProfile) |  |  |
| banners | [NewsBanner](#sogage-v1-NewsBanner) | repeated |  |
| presents | [PresentBoxItem](#sogage-v1-PresentBoxItem) | repeated |  |
| counters | [GetHomeResponse.CountersEntry](#sogage-v1-GetHomeResponse-CountersEntry) | repeated | 例: {"unread_news": 3, "unclaimed_presents": 10} |






<a name="sogage-v1-GetHomeResponse-CountersEntry"></a>

### GetHomeResponse.CountersEntry



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| key | [string](#string) |  |  |
| value | [int64](#int64) |  |  |






<a name="sogage-v1-GuestIdentity"></a>

### GuestIdentity



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| device_id | [string](#string) |  |  |






<a name="sogage-v1-LoginRequest"></a>

### LoginRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| device | [DeviceInfo](#sogage-v1-DeviceInfo) |  |  |
| guest | [GuestIdentity](#sogage-v1-GuestIdentity) |  |  |
| oauth | [OAuthIdentity](#sogage-v1-OAuthIdentity) |  |  |
| apple | [AppleIdentity](#sogage-v1-AppleIdentity) |  |  |
| client_meta | [LoginRequest.ClientMetaEntry](#sogage-v1-LoginRequest-ClientMetaEntry) | repeated | 例: {"locale": "ja-JP", "tz": "Asia/Tokyo"} |






<a name="sogage-v1-LoginRequest-ClientMetaEntry"></a>

### LoginRequest.ClientMetaEntry



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| key | [string](#string) |  |  |
| value | [string](#string) |  |  |






<a name="sogage-v1-LoginResponse"></a>

### LoginResponse



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| meta | [ResponseMeta](#sogage-v1-ResponseMeta) |  |  |
| access_token | [string](#string) |  |  |
| expires_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  |  |
| profile | [PlayerProfile](#sogage-v1-PlayerProfile) |  |  |
| is_new | [bool](#bool) |  |  |
| welcome_rewards | [Reward](#sogage-v1-Reward) | repeated |  |






<a name="sogage-v1-NewsBanner"></a>

### NewsBanner



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| banner_id | [string](#string) |  |  |
| title | [string](#string) |  |  |
| image_url | [string](#string) |  |  |
| start_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  |  |
| end_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  |  |
| extras | [NewsBanner.ExtrasEntry](#sogage-v1-NewsBanner-ExtrasEntry) | repeated |  |






<a name="sogage-v1-NewsBanner-ExtrasEntry"></a>

### NewsBanner.ExtrasEntry



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| key | [string](#string) |  |  |
| value | [string](#string) |  |  |






<a name="sogage-v1-OAuthIdentity"></a>

### OAuthIdentity



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| provider | [string](#string) |  | 例: "google", "facebook" |
| id_token | [string](#string) |  |  |






<a name="sogage-v1-PaidCurrencyPayment"></a>

### PaidCurrencyPayment



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| currency_type | [CurrencyType](#sogage-v1-CurrencyType) |  |  |
| unit_price | [int64](#int64) |  |  |






<a name="sogage-v1-PresentBoxItem"></a>

### PresentBoxItem



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| present_id | [string](#string) |  |  |
| reward | [Reward](#sogage-v1-Reward) |  |  |
| received_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  |  |
| expires_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  |  |
| claimed | [bool](#bool) |  |  |






<a name="sogage-v1-PurchaseProductRequest"></a>

### PurchaseProductRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| access_token | [string](#string) |  |  |
| product_id | [string](#string) |  |  |
| quantity | [int32](#int32) |  |  |
| applied_coupon_ids | [string](#string) | repeated |  |
| currency | [CurrencyPayment](#sogage-v1-CurrencyPayment) |  |  |
| store | [StoreReceiptPayment](#sogage-v1-StoreReceiptPayment) |  |  |






<a name="sogage-v1-PurchaseProductResponse"></a>

### PurchaseProductResponse



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| meta | [ResponseMeta](#sogage-v1-ResponseMeta) |  |  |
| order_id | [string](#string) |  |  |
| rewards | [Reward](#sogage-v1-Reward) | repeated |  |
| inventory_delta | [PurchaseProductResponse.InventoryDeltaEntry](#sogage-v1-PurchaseProductResponse-InventoryDeltaEntry) | repeated | 例: {"item:ticket_10": 1, "unit:hero_001": 1} |






<a name="sogage-v1-PurchaseProductResponse-InventoryDeltaEntry"></a>

### PurchaseProductResponse.InventoryDeltaEntry



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| key | [string](#string) |  |  |
| value | [int64](#int64) |  |  |






<a name="sogage-v1-StartQuestRequest"></a>

### StartQuestRequest



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| access_token | [string](#string) |  |  |
| quest_id | [string](#string) |  |  |
| deck_id | [string](#string) |  |  |
| support_unit_ids | [string](#string) | repeated |  |
| client_params | [StartQuestRequest.ClientParamsEntry](#sogage-v1-StartQuestRequest-ClientParamsEntry) | repeated | 例: {"latency_ms": "23", "net": "wifi"} |






<a name="sogage-v1-StartQuestRequest-ClientParamsEntry"></a>

### StartQuestRequest.ClientParamsEntry



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| key | [string](#string) |  |  |
| value | [string](#string) |  |  |






<a name="sogage-v1-StartQuestResponse"></a>

### StartQuestResponse



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| meta | [ResponseMeta](#sogage-v1-ResponseMeta) |  |  |
| quest_session_id | [string](#string) |  |  |
| started_at | [google.protobuf.Timestamp](#google-protobuf-Timestamp) |  |  |
| seed | [int64](#int64) |  |  |
| enemy_unit_ids | [string](#string) | repeated |  |






<a name="sogage-v1-StoreReceiptPayment"></a>

### StoreReceiptPayment



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| store_type | [StoreType](#sogage-v1-StoreType) |  |  |
| receipt | [string](#string) |  |  |
| transaction_id | [string](#string) |  |  |






<a name="sogage-v1-TicketPayment"></a>

### TicketPayment



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticket_item_id | [string](#string) |  |  |





 <!-- end messages -->

 <!-- end enums -->

 <!-- end HasExtensions -->



## Scalar Value Types

| .proto Type | Notes | C++ | Java | Python | Go | C# | PHP | Ruby |
| ----------- | ----- | --- | ---- | ------ | -- | -- | --- | ---- |
| <a name="double" /> double |  | double | double | float | float64 | double | float | Float |
| <a name="float" /> float |  | float | float | float | float32 | float | float | Float |
| <a name="int32" /> int32 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint32 instead. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="int64" /> int64 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint64 instead. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="uint32" /> uint32 | Uses variable-length encoding. | uint32 | int | int/long | uint32 | uint | integer | Bignum or Fixnum (as required) |
| <a name="uint64" /> uint64 | Uses variable-length encoding. | uint64 | long | int/long | uint64 | ulong | integer/string | Bignum or Fixnum (as required) |
| <a name="sint32" /> sint32 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int32s. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="sint64" /> sint64 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int64s. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="fixed32" /> fixed32 | Always four bytes. More efficient than uint32 if values are often greater than 2^28. | uint32 | int | int | uint32 | uint | integer | Bignum or Fixnum (as required) |
| <a name="fixed64" /> fixed64 | Always eight bytes. More efficient than uint64 if values are often greater than 2^56. | uint64 | long | int/long | uint64 | ulong | integer/string | Bignum |
| <a name="sfixed32" /> sfixed32 | Always four bytes. | int32 | int | int | int32 | int | integer | Bignum or Fixnum (as required) |
| <a name="sfixed64" /> sfixed64 | Always eight bytes. | int64 | long | int/long | int64 | long | integer/string | Bignum |
| <a name="bool" /> bool |  | bool | boolean | boolean | bool | bool | boolean | TrueClass/FalseClass |
| <a name="string" /> string | A string must always contain UTF-8 encoded or 7-bit ASCII text. | string | String | str/unicode | string | string | string | String (UTF-8) |
| <a name="bytes" /> bytes | May contain any arbitrary sequence of bytes. | string | ByteString | str | []byte | ByteString | string | String (ASCII-8BIT) |

