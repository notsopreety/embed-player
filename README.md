# embed-player
A HTML based embed player supports iframe for websites.


## Postgresql Table Schema
```sql
CREATE TABLE videos (
  id integer NOT NULL DEFAULT nextval('videos_id_seq'::regclass),
  video_id character varying NOT NULL UNIQUE,
  title character varying NOT NULL,
  url text NOT NULL,
  created_by integer,
  created_at timestamp with time zone DEFAULT CURRENT_TIMESTAMP,
  CONSTRAINT videos_pkey PRIMARY KEY (id),
  CONSTRAINT videos_created_by_fkey FOREIGN KEY (created_by) REFERENCES public.users(id)
);
```
