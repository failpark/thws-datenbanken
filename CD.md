# CD Verwaltung

## 1

```mermaid
erDiagram
	Song {
		int id PK
		string name
	}
	%% Artist = Interpret
	Artist {
		int id PK
		string name
	}
	Track {
		int song_id FK
		int artist_id FK
		int length "in secs"
	}
	CD {
		int id PK
		string name
		int length "in secs"
	}
	Genre {
		int id PK
		string name UK
	}
	Track-to-CD {
		int id PK
		int track_id FK
		int cd_id FK
		int sort_order
	}
	Genre-to-CD {
		int id PK
		int cd_id FK
		int genre_id FK
	}
	Track ||--|{ Song :"belongs to"
	Artist ||--|{ Track:"sings"
	CD ||--|{ Track-to-CD :"contains"
	Track ||--|{ Track-to-CD :"in"
	Genre ||--|{ Genre-to-CD :"has"
	CD ||--|{ Genre-to-CD :"has"
```

## 2

### Song
#### Schlüsselkandidaten
- id
- name
#### Primärschlüssel
id
#### Fremdschlüssel
keiner
### Artist
#### Schlüsselkandidaten
- id
- name
#### Primärschlüssel
id
#### Fremdschlüssel
keiner
### CD
#### Schlüsselkandidaten
- id
- name
#### Primärschlüssel
- id
#### Fremdschlüssel
keiner
### Genre
#### Schlüsselkandidaten
- id
- name
#### Primärschlüssel
id
#### Fremdschlüssel
keiner
### Song-to-CD
#### Schlüsselkandidaten
- id
- song_id, cd_id
#### Primärschlüssel
id
#### Fremdschlüssel
- song_id
- cd_id
### Song-to-Artist
#### Schlüsselkandidaten
- id
- song_id, artist_id
#### Primärschlüssel
id
#### Fremdschlüssel
- song_id
- artist_id
### Genre-to-CD
#### Schlüsselkandidaten
- id
- genre_id, cd_id
#### Primärschlüssel
id
#### Fremdschlüssel
- genre_id
- cd_id

## 3

- length der cd (kann berechnet werden)
