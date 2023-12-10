# High Peak Council

Support for schedules provided by [High Peak Council](https://www.highpeak.gov.uk/findyourbinday/), For High Peak council.

## Configuration is done via configuration.yaml

(recommended)

```yaml
waste_collection_schedule:
    sources:
    - name: high_peak_uk
      args:
        premises_id: PREMISES_ID
```

or (not recommended)

```yaml
waste_collection_schedule:
    sources:
        - name: high_peak_uk
          args:
            post_code: SK13 1BW
            house_number: 221
```

### Configuration Variables

**premises_id**  
*(int) (required if post_code not provided)*

**post_code**  
*(string) (required if premises_id not provided)*

**house_number**  
*(int) (required if premises_id not provided)*

## Example

```yaml
waste_collection_schedule:
    sources:
    - name: high_peak_uk
      args:
        premises_id: 71b6cce0-06e1-43e5-999c-56e4f84e3142&fsn=2306292b-e07d-4ba9-b899-ea50d0c98a70
```

## How to get the premises_id argument

The premises_id can be found in the URL when looking up your
bin collection days at after the "=" [High Peak Councils bin day page](https://www.highpeak.gov.uk/findyourbinday/).

## Why premises_id over post_code and house number?

The code has to do a search by post code and house number then look up the bin collection time using premises ID.