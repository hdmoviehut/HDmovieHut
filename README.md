CREATE TABLE media (
    id SERIAL PRIMARY KEY,
    type VARCHAR(10) NOT NULL CHECK (type IN ('movie','tv')),
    title TEXT NOT NULL,
    description TEXT,
    thumbnail TEXT,
    backdrop TEXT,
    release_date DATE,
    language VARCHAR(10),
    rating NUMERIC(3,1),
    status TEXT, -- TV series status (Ongoing, Finished, Cancelled, etc.)
    
    -- NEW FEATURES START HERE:
    source_type VARCHAR(20) DEFAULT 'original', -- NEW: Source type (camcopy, original, bluray, webrip, etc.)
    youtube_trailer TEXT, -- NEW: YouTube trailer URL
    screenshots_720p JSONB DEFAULT '[]', -- NEW: 720p screenshots array
    screenshots_1080p JSONB DEFAULT '[]', -- NEW: 1080p screenshots array
    screenshots_2160p JSONB DEFAULT '[]', -- NEW: 2160p screenshots array
    screenshots_trailer JSONB DEFAULT '[]', -- NEW: Trailer screenshots array
    -- NEW FEATURES END HERE
    
    cast_members JSON,
    video_links JSON,
    download_links JSON,
    telegram_links JSON, -- Telegram download links
    torrent_links JSON,
    total_seasons INT,
    seasons JSON,
    genres JSON,
    file_type VARCHAR(20) DEFAULT 'webrip'
);



working 😔 💪 
