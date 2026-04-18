from fastapi.staticfiles import StaticFiles
from fastapi import FastAPI, UploadFile
import os
import subprocess
import uuid

app = FastAPI()

app.mount("/temp", StaticFiles(directory="temp"), name="temp")

os.makedirs("temp", exist_ok=True)

@app.get("/")
def home():
    return {"message": "Server running"}

@app.post("/upload")
async def upload(file: UploadFile):
    file_path = f"temp/{file.filename}"

    with open(file_path, "wb") as f:
        f.write(await file.read())

    # 🔥 Hardcoded clip times (for demo)
    highlights = [
        {"start": 5, "end": 10},
        {"start": 15, "end": 20}
    ]

    output_files = []

    for h in highlights:
        output_name = f"temp/{uuid.uuid4()}.mp4"

        command = [
            "ffmpeg",
            "-i", file_path,
            "-ss", str(h["start"]),
            "-to", str(h["end"]),
            "-c:v", "libx264",
            "-c:a", "aac",
            output_name
        ]

        subprocess.run(command)

        output_files.append(output_name)

    return {"clips": output_files}
