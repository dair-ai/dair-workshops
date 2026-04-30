# Raw Source: DeepSeek Function Calling
# Fetched: 2026-04-28
# Source: https://api-docs.deepseek.com/guides/function_calling

Key concepts:
- OpenAI SDK compatible (different base_url)
- Strict mode (beta): use base_url="https://api.deepseek.com/beta"
- All object properties must be required, additionalProperties: false
- Supported JSON schema: object, string, number, integer, boolean, array, enum, anyOf
- Unsupported: minLength, maxLength, minItems, maxItems
- $ref and $def for modular/reusable schemas
- String formats: email, hostname, ipv4, ipv6, uuid
- Number constraints: minimum, maximum, exclusiveMinimum, exclusiveMaximum, multipleOf