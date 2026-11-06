# MASTER PROJECT SPECIFICATION

# AI-AUTO-EDITING-LOCALIZATION-STUDIO

# ULTIMATE COMPLETE APPLICATION BLUEPRINT

> **Project:** AI-Auto-Editing-Localization-Studio\
> **Target version:** Ultimate 1.0\
> **Product:** Professional AI automatic video editing, production and
> localization platform\
> **Architecture:** Modular Hybrid AI\
> **Frontend:** React + TypeScript + Vite\
> **Backend:** Node.js + Express (adapt to the existing backend if
> different)\
> **Media processing:** FFmpeg + FFprobe + optional OpenCV adapters\
> **AI:** Cloud AI + open-source AI + local AI adapters\
> **Database:** PostgreSQL-compatible architecture; SQLite may be used
> for development\
> **Storage:** Local and cloud storage adapters\
> **Default localization:** Egyptian Arabic (`ar-EG`)

## 00 --- Executive project definition

The application lets a user upload a source video and automatically
carries out the production workflow:

**Upload → Analyze → Understand → Edit → Localize → Enhance → Render →
Quality Control → Export**

Supported deliverables include long-form videos, YouTube Shorts,
Instagram Reels, TikTok videos, square videos and custom aspect ratios.

This is an incremental upgrade specification for the existing
repository. It is not authorization to replace the project or discard
working code.

------------------------------------------------------------------------

## 01 --- Master repository structure

``` text
AI-Auto-Editing-Localization-Studio/
├── README.md
├── CHANGELOG.md
├── LICENSE
├── SECURITY.md
├── CONTRIBUTING.md
├── .gitignore
├── .env.example
├── package.json
├── package-lock.json
├── tsconfig.json
├── vite.config.ts
├── index.html
├── eslint.config.js
├── vitest.config.ts
├── playwright.config.ts
├── Dockerfile
├── docker-compose.yml
│
├── public/
│   ├── favicon.ico
│   ├── logo.svg
│   ├── manifest.json
│   ├── images/
│   ├── icons/
│   ├── fonts/
│   └── presets/
│
├── docs/
│   ├── MASTER_BLUEPRINT.md
│   ├── ARCHITECTURE.md
│   ├── REPOSITORY_MAP.md
│   ├── DATABASE_SCHEMA.md
│   ├── API_REFERENCE.md
│   ├── ENGINE_REFERENCE.md
│   ├── AI_PROVIDER_GUIDE.md
│   ├── VIDEO_PIPELINE.md
│   ├── AUDIO_PIPELINE.md
│   ├── LOCALIZATION_GUIDE.md
│   ├── RENDERING_GUIDE.md
│   ├── TESTING_GUIDE.md
│   ├── SECURITY_GUIDE.md
│   └── DEPLOYMENT_GUIDE.md
│
├── src/
│   ├── main.tsx
│   ├── App.tsx
│   ├── app/
│   │   ├── AppProvider.tsx
│   │   ├── AppInitializer.ts
│   │   ├── AppConfiguration.ts
│   │   ├── AppRegistry.ts
│   │   ├── ErrorBoundary.tsx
│   │   ├── router/
│   │   │   ├── index.tsx
│   │   │   ├── routes.ts
│   │   │   └── navigation.ts
│   │   └── providers/
│   │       ├── ThemeProvider.tsx
│   │       ├── LanguageProvider.tsx
│   │       ├── ProjectProvider.tsx
│   │       └── AIProviderContext.tsx
│   │
│   ├── layouts/
│   │   ├── MainLayout.tsx
│   │   ├── DashboardLayout.tsx
│   │   ├── StudioLayout.tsx
│   │   ├── EditorLayout.tsx
│   │   └── MobileLayout.tsx
│   │
│   ├── pages/
│   │   ├── DashboardPage.tsx
│   │   ├── ProjectsPage.tsx
│   │   ├── ProjectDetailsPage.tsx
│   │   ├── ImportPage.tsx
│   │   ├── StudioWorkspace.tsx
│   │   ├── AutomaticStudioPage.tsx
│   │   ├── TimelineEditorPage.tsx
│   │   ├── VideoAnalysisPage.tsx
│   │   ├── CharacterStudioPage.tsx
│   │   ├── EnvironmentStudioPage.tsx
│   │   ├── AudioStudioPage.tsx
│   │   ├── VoiceStudioPage.tsx
│   │   ├── SubtitleStudioPage.tsx
│   │   ├── LocalizationPage.tsx
│   │   ├── EffectsStudioPage.tsx
│   │   ├── ColorGradingPage.tsx
│   │   ├── EnhancementPage.tsx
│   │   ├── ShortsStudioPage.tsx
│   │   ├── LongVideoStudioPage.tsx
│   │   ├── RenderingPage.tsx
│   │   ├── ExportCenterPage.tsx
│   │   ├── TemplatesPage.tsx
│   │   ├── MediaLibraryPage.tsx
│   │   ├── AIProvidersPage.tsx
│   │   ├── ModelManagementPage.tsx
│   │   ├── StoragePage.tsx
│   │   ├── UsagePage.tsx
│   │   └── SettingsPage.tsx
│   │
│   ├── components/
│   │   ├── common/
│   │   │   ├── Button.tsx
│   │   │   ├── Modal.tsx
│   │   │   ├── Dropdown.tsx
│   │   │   ├── Tooltip.tsx
│   │   │   ├── ProgressBar.tsx
│   │   │   ├── StatusBadge.tsx
│   │   │   ├── LoadingState.tsx
│   │   │   ├── ErrorState.tsx
│   │   │   └── ConfirmDialog.tsx
│   │   ├── navigation/
│   │   │   ├── Sidebar.tsx
│   │   │   ├── Topbar.tsx
│   │   │   └── MobileNavigation.tsx
│   │   ├── dashboard/
│   │   │   ├── ProjectStatistics.tsx
│   │   │   ├── RecentProjects.tsx
│   │   │   ├── ActiveJobs.tsx
│   │   │   ├── EngineStatus.tsx
│   │   │   ├── StorageOverview.tsx
│   │   │   └── QuickActions.tsx
│   │   ├── media/
│   │   │   ├── MediaUploader.tsx
│   │   │   ├── MediaBrowser.tsx
│   │   │   ├── MediaPreview.tsx
│   │   │   ├── MediaMetadata.tsx
│   │   │   └── UploadProgress.tsx
│   │   ├── video-player/
│   │   │   ├── VideoPlayer.tsx
│   │   │   ├── PlayerControls.tsx
│   │   │   └── FramePreview.tsx
│   │   ├── timeline/
│   │   │   ├── Timeline.tsx
│   │   │   ├── TimelineRuler.tsx
│   │   │   ├── TimelineCanvas.tsx
│   │   │   ├── TimelinePlayhead.tsx
│   │   │   ├── TimelineToolbar.tsx
│   │   │   └── TimelineZoom.tsx
│   │   ├── tracks/
│   │   │   ├── VideoTrack.tsx
│   │   │   ├── AudioTrack.tsx
│   │   │   ├── SubtitleTrack.tsx
│   │   │   ├── EffectsTrack.tsx
│   │   │   └── TrackControls.tsx
│   │   ├── clips/
│   │   │   ├── TimelineClip.tsx
│   │   │   ├── ClipTrimmer.tsx
│   │   │   └── ClipInspector.tsx
│   │   ├── audio/
│   │   │   ├── AudioMixer.tsx
│   │   │   ├── AudioWaveform.tsx
│   │   │   ├── Equalizer.tsx
│   │   │   └── AudioEffectsPanel.tsx
│   │   ├── subtitles/
│   │   │   ├── SubtitleEditor.tsx
│   │   │   ├── SubtitlePreview.tsx
│   │   │   └── SubtitleStylePanel.tsx
│   │   ├── characters/
│   │   │   ├── CharacterCard.tsx
│   │   │   ├── CharacterProfile.tsx
│   │   │   ├── CharacterReferences.tsx
│   │   │   └── ConsistencyReport.tsx
│   │   └── rendering/
│   │       ├── RenderQueue.tsx
│   │       ├── RenderJobCard.tsx
│   │       ├── RenderProgress.tsx
│   │       └── ExportPanel.tsx
│   │
│   ├── features/
│   │   ├── projects/
│   │   ├── import/
│   │   ├── analysis/
│   │   ├── automatic-editing/
│   │   ├── timeline/
│   │   ├── character-consistency/
│   │   ├── environment-consistency/
│   │   ├── audio/
│   │   ├── voice/
│   │   ├── translation/
│   │   ├── localization/
│   │   ├── subtitles/
│   │   ├── effects/
│   │   ├── enhancement/
│   │   ├── shorts/
│   │   ├── long-video/
│   │   └── export/
│   │
│   ├── services/
│   │   ├── api/
│   │   │   ├── apiClient.ts
│   │   │   └── apiConfig.ts
│   │   ├── ProjectService.ts
│   │   ├── MediaService.ts
│   │   ├── UploadService.ts
│   │   ├── AnalysisService.ts
│   │   ├── EditingService.ts
│   │   ├── TimelineService.ts
│   │   ├── AudioService.ts
│   │   ├── VoiceService.ts
│   │   ├── TranslationService.ts
│   │   ├── SubtitleService.ts
│   │   ├── CharacterService.ts
│   │   ├── RenderingService.ts
│   │   └── ExportService.ts
│   │
│   ├── stores/
│   │   ├── appStore.ts
│   │   ├── projectStore.ts
│   │   ├── mediaStore.ts
│   │   ├── timelineStore.ts
│   │   ├── audioStore.ts
│   │   ├── editingStore.ts
│   │   ├── characterStore.ts
│   │   ├── renderStore.ts
│   │   └── settingsStore.ts
│   │
│   ├── hooks/
│   │   ├── useProject.ts
│   │   ├── useUpload.ts
│   │   ├── useTimeline.ts
│   │   ├── useRendering.ts
│   │   └── useAutosave.ts
│   │
│   ├── types/
│   │   ├── project.types.ts
│   │   ├── media.types.ts
│   │   ├── scene.types.ts
│   │   ├── timeline.types.ts
│   │   ├── character.types.ts
│   │   ├── audio.types.ts
│   │   ├── subtitle.types.ts
│   │   ├── rendering.types.ts
│   │   └── provider.types.ts
│   │
│   ├── i18n/
│   │   ├── index.ts
│   │   ├── ar-EG.json
│   │   ├── ar.json
│   │   └── en.json
│   │
│   ├── workers/
│   │   ├── thumbnail.worker.ts
│   │   ├── waveform.worker.ts
│   │   └── analysis.worker.ts
│   │
│   ├── utils/
│   │   ├── timecode.ts
│   │   ├── mediaUtils.ts
│   │   ├── fileValidation.ts
│   │   ├── errorHandler.ts
│   │   └── logger.ts
│   │
│   └── styles/
│       ├── globals.css
│       ├── variables.css
│       ├── themes.css
│       ├── responsive.css
│       ├── animations.css
│       └── rtl.css
│
├── server/
│   ├── index.js
│   ├── app.js
│   ├── api/
│   │   ├── routes/
│   │   │   ├── health.routes.js
│   │   │   ├── projects.routes.js
│   │   │   ├── media.routes.js
│   │   │   ├── upload.routes.js
│   │   │   ├── analysis.routes.js
│   │   │   ├── editing.routes.js
│   │   │   ├── timeline.routes.js
│   │   │   ├── characters.routes.js
│   │   │   ├── audio.routes.js
│   │   │   ├── voice.routes.js
│   │   │   ├── translation.routes.js
│   │   │   ├── localization.routes.js
│   │   │   ├── subtitles.routes.js
│   │   │   ├── shorts.routes.js
│   │   │   ├── long-video.routes.js
│   │   │   ├── rendering.routes.js
│   │   │   ├── exports.routes.js
│   │   │   └── providers.routes.js
│   │   ├── controllers/
│   │   ├── middleware/
│   │   └── validators/
│   ├── orchestrator/
│   │   ├── JobOrchestrator.js
│   │   ├── PipelineManager.js
│   │   ├── WorkflowManager.js
│   │   ├── TaskScheduler.js
│   │   ├── JobQueue.js
│   │   ├── JobRegistry.js
│   │   ├── JobStateManager.js
│   │   ├── RetryManager.js
│   │   ├── RecoveryManager.js
│   │   ├── CancellationManager.js
│   │   └── ProgressManager.js
│   ├── providers/
│   │   ├── ProviderRegistry.js
│   │   ├── ProviderManager.js
│   │   ├── ProviderRouter.js
│   │   ├── ProviderHealth.js
│   │   ├── ModelRegistry.js
│   │   ├── ModelSelector.js
│   │   └── adapters/
│   │       ├── BaseProviderAdapter.js
│   │       ├── GeminiAdapter.js
│   │       ├── OpenAICompatibleAdapter.js
│   │       ├── LocalModelAdapter.js
│   │       ├── WhisperAdapter.js
│   │       └── TTSAdapter.js
│   ├── storage/
│   │   ├── MediaStorage.js
│   │   ├── ProjectStorage.js
│   │   ├── TemporaryStorage.js
│   │   ├── CacheStorage.js
│   │   └── StorageQuota.js
│   ├── database/
│   │   ├── connection.js
│   │   ├── migrations/
│   │   ├── schemas/
│   │   ├── repositories/
│   │   └── seeds/
│   ├── security/
│   │   ├── Authentication.js
│   │   ├── Authorization.js
│   │   ├── SecretsManager.js
│   │   ├── Encryption.js
│   │   ├── FileSecurity.js
│   │   └── RateLimiter.js
│   ├── monitoring/
│   │   ├── Logger.js
│   │   ├── Metrics.js
│   │   ├── HealthCheck.js
│   │   └── PerformanceMonitor.js
│   └── tests/
│
├── engines/
│   ├── content_discovery_engine/
│   ├── lesson_parser_engine/
│   ├── video_intelligence/
│   ├── scene_detection/
│   ├── story_intelligence/
│   ├── editing_decision/
│   ├── automatic_editing/
│   ├── timeline/
│   ├── character_consistency/
│   ├── environment_consistency/
│   ├── audio_intelligence/
│   ├── audio_processing/
│   ├── voice_studio/
│   ├── translation/
│   ├── localization/
│   ├── subtitles/
│   ├── effects/
│   ├── color_grading/
│   ├── enhancement/
│   ├── shorts_generation/
│   ├── long_video/
│   ├── rendering/
│   ├── quality_control/
│   ├── adaptive_learning_engine/
│   ├── ai_tutor_engine/
│   ├── mcq_generation_engine/
│   ├── smart_mcq_engine/
│   ├── search_engine/
│   ├── progress_engine/
│   ├── recommendation_engine/
│   ├── dashboard_engine/
│   └── guardian_engine/
│
├── integrations/
│   ├── ffmpeg/
│   ├── ffprobe/
│   ├── opencv/
│   ├── whisper/
│   ├── speech/
│   ├── vision/
│   ├── translation/
│   ├── upscaling/
│   └── cloud/
│
├── database/
│   ├── schema.sql
│   ├── migrations/
│   ├── seeds/
│   ├── repositories/
│   └── indexes/
│
├── config/
│   ├── app.config.ts
│   ├── server.config.ts
│   ├── ai.config.ts
│   ├── video.config.ts
│   ├── audio.config.ts
│   ├── render.config.ts
│   ├── storage.config.ts
│   ├── security.config.ts
│   └── localization.config.ts
│
├── templates/
│   ├── editing/
│   │   ├── cinematic.json
│   │   ├── documentary.json
│   │   ├── podcast.json
│   │   ├── educational.json
│   │   ├── social-media.json
│   │   ├── anime.json
│   │   └── professional.json
│   ├── subtitles/
│   ├── transitions/
│   ├── effects/
│   ├── color-luts/
│   ├── shorts/
│   └── export/
│
├── tests/
│   ├── unit/
│   ├── integration/
│   ├── e2e/
│   ├── performance/
│   ├── security/
│   ├── recovery/
│   ├── fixtures/
│   └── helpers/
│
├── scripts/
│   ├── check-environment.js
│   ├── validate-architecture.js
│   ├── run-tests.js
│   ├── migrate-database.js
│   └── clean-cache.js
│
├── deployment/
│   ├── docker/
│   ├── cloud/
│   ├── web/
│   └── mobile/
│
└── .github/
    └── workflows/
        ├── ci.yml
        ├── tests.yml
        ├── build.yml
        └── security.yml
```

**Repository structure note:** This is the target architecture, not a
claim that every listed file currently exists. The existing repository's
language, folder conventions, server entry points and modules take
precedence. Do not create a second orchestrator or duplicate existing
engines. The `content_discovery_engine`, `lesson_parser_engine`,
`adaptive_learning_engine`, `ai_tutor_engine`, `mcq_generation_engine`,
`smart_mcq_engine`, `search_engine`, `progress_engine`,
`recommendation_engine`, `dashboard_engine` and `guardian_engine`
entries should only remain if they genuinely belong to this product;
otherwise preserve them only if they are already used by the current
application, and do not connect unrelated nursing-app functionality to
the video workflow.

------------------------------------------------------------------------

## 02 --- Engine specifications

Each implemented engine should expose an entry point, configuration,
types/interfaces, service implementation, validation, error definitions
and tests. Follow the repository's existing language and conventions; do
not force JavaScript files into a TypeScript-only architecture or vice
versa.

### Engine 01: Video Intelligence

-   Extract video metadata.
-   Sample and extract representative frames.
-   Understand visual content.
-   Detect objects and people.
-   Detect faces where appropriate.
-   Analyze motion and actions.
-   Perform OCR.
-   Classify content.
-   Generate video summaries.

### Engine 02: Scene Detection

-   Detect scene and shot boundaries.
-   Detect transitions.
-   Detect black and frozen frames.
-   Classify scenes.
-   Select keyframes.
-   Construct a scene timeline.

### Engine 03: Story Intelligence

-   Extract narrative structure.
-   Sequence events.
-   Detect story arcs, hooks, climaxes and resolutions.
-   Analyze dialogue.
-   Detect continuity issues.
-   Generate narrative summaries.

### Engine 04: Editing Decision

-   Decide cuts and clip selection.
-   Determine pacing.
-   Select transitions.
-   Place audio and music.
-   Score highlights.
-   Validate the proposed edit plan.

### Engine 05: Automatic Editing

-   Smart cutting and trimming.
-   Silence and dead-air detection.
-   Jump cuts where appropriate.
-   Automatic zoom and stabilization.
-   Smart reframing.
-   Highlight extraction.
-   B-roll selection when suitable assets exist.
-   Preserve story flow.

### Engine 06: Timeline

-   Multi-track management.
-   Clip and audio synchronization.
-   Subtitle synchronization.
-   Keyframes and transitions.
-   Undo and redo.
-   Non-destructive editing.
-   Timeline serialization and versioning.

### Engine 07: Character Consistency

-   Detect recurring characters.
-   Create character profiles.
-   Track appearances.
-   Analyze clothing and visual attributes.
-   Match identity references.
-   Report continuity confidence and mismatches.

### Engine 08: Environment Consistency

-   Detect locations and backgrounds.
-   Analyze lighting and color.
-   Track object placement when feasible.
-   Compare scene environments.
-   Report spatial and visual continuity warnings.

### Engine 09: Audio Intelligence

-   Detect speech and music.
-   Recognize speech.
-   Identify speakers.
-   Detect silence, noise and audio classes.

### Engine 10: Audio Processing

-   Noise and echo reduction.
-   Voice enhancement.
-   Equalization.
-   Compression and limiting.
-   Loudness normalization.
-   Audio ducking and mixing.

### Engine 11: Voice Studio

-   Text-to-speech.
-   Speaker assignment.
-   Voice profiles.
-   Speech-rate controls.
-   Dialogue generation.
-   Audio synchronization.
-   Voice cloning only with appropriate authorization and consent.

### Engine 12: Translation

-   Language detection.
-   Context-aware translation.
-   Terminology management.
-   Translation validation.
-   Translation memory.

### Engine 13: Localization

-   Cultural adaptation.
-   Egyptian Arabic localization.
-   Dialect selection.
-   Natural dialogue rewriting.
-   Preserve context, speaker personality and timing.

### Engine 14: Subtitles

-   Automatic transcription.
-   Word-level timestamps when supported.
-   Subtitle segmentation.
-   Translation.
-   Styling and rendering.
-   Timing validation.
-   SRT, VTT and ASS export.

### Engine 15: Effects

-   Transitions.
-   Blur, glow and motion blur.
-   Film grain and vignette.
-   Compositing and overlays.
-   Motion graphics.

### Engine 16: Color Grading

-   Exposure and contrast.
-   White balance.
-   Saturation, temperature and tint.
-   LUT application.
-   Scene-to-scene color matching.

### Engine 17: Enhancement

-   Upscaling.
-   Denoising and sharpening.
-   Frame interpolation.
-   Deflickering.
-   Stabilization and restoration.

### Engine 18: Shorts Generation

-   Detect highlights and hooks.
-   Extract independent clips.
-   Reframe vertically.
-   Track faces where supported.
-   Generate captions.
-   Validate clip boundaries.
-   Detect duplicate or highly overlapping clips.

### Engine 19: Long Video

-   Preserve narrative.
-   Assemble story structure.
-   Generate chapters.
-   Maintain long-form pacing and audio continuity.

### Engine 20: Rendering

-   Manage render queue and scheduling.
-   Execute FFmpeg jobs.
-   Apply encoding profiles.
-   Support segmented rendering.
-   Resume, cancel and recover jobs where feasible.

### Engine 21: Quality Control

-   Validate video and audio integrity.
-   Check subtitle synchronization.
-   Detect black/frozen frames.
-   Validate codecs and encoding.
-   Check continuity.
-   Generate final quality reports.

------------------------------------------------------------------------

## 03 --- Complete data models

The following are canonical model shapes. Implement them using the
repository's actual type system and database conventions. Add validation
and migrations rather than storing unvalidated arbitrary objects.

### Project

``` json
{
  "id": "uuid",
  "name": "string",
  "description": "string",
  "status": "draft",
  "createdAt": "datetime",
  "updatedAt": "datetime",
  "sourceMediaIds": [],
  "timelineId": "uuid",
  "settings": {},
  "outputs": [],
  "metadata": {}
}
```

### Media

``` json
{
  "id": "uuid",
  "projectId": "uuid",
  "fileName": "string",
  "mimeType": "string",
  "fileSize": 0,
  "duration": 0,
  "width": 0,
  "height": 0,
  "fps": 0,
  "codec": "string",
  "audioTracks": [],
  "videoTracks": [],
  "storagePath": "string",
  "checksum": "string",
  "status": "uploaded",
  "createdAt": "datetime"
}
```

### Scene

``` json
{
  "id": "uuid",
  "projectId": "uuid",
  "sourceMediaId": "uuid",
  "startTime": 0,
  "endTime": 0,
  "duration": 0,
  "description": "string",
  "sceneType": "unknown",
  "keyframes": [],
  "characters": [],
  "environmentId": "uuid",
  "importanceScore": 0,
  "confidence": 0
}
```

### Character

``` json
{
  "id": "uuid",
  "projectId": "uuid",
  "name": "string",
  "description": "string",
  "referenceImages": [],
  "appearance": {},
  "clothing": {},
  "voiceProfileId": "uuid",
  "sceneAppearances": [],
  "consistencyScore": 0,
  "createdAt": "datetime"
}
```

### Environment

``` json
{
  "id": "uuid",
  "projectId": "uuid",
  "locationDescription": "string",
  "background": {},
  "lighting": {},
  "colorPalette": [],
  "weather": "unknown",
  "timeOfDay": "unknown",
  "sceneReferences": []
}
```

### Timeline

``` json
{
  "id": "uuid",
  "projectId": "uuid",
  "duration": 0,
  "frameRate": 30,
  "timebase": "1/30",
  "tracks": [],
  "markers": [],
  "version": 1,
  "updatedAt": "datetime"
}
```

### Track

``` json
{
  "id": "uuid",
  "type": "video",
  "name": "string",
  "order": 0,
  "muted": false,
  "locked": false,
  "clips": []
}
```

### Clip

``` json
{
  "id": "uuid",
  "sourceMediaId": "uuid",
  "sourceStart": 0,
  "sourceEnd": 0,
  "timelineStart": 0,
  "timelineEnd": 0,
  "trackId": "uuid",
  "effects": [],
  "transitions": [],
  "keyframes": []
}
```

### Editing decision

``` json
{
  "id": "uuid",
  "type": "cut",
  "sourceSceneIds": [],
  "timestamp": 0,
  "reason": "string",
  "confidence": 0,
  "parameters": {},
  "status": "pending",
  "reversible": true
}
```

### Audio segment

``` json
{
  "id": "uuid",
  "startTime": 0,
  "endTime": 0,
  "speakerId": "uuid",
  "transcript": "string",
  "language": "string",
  "audioFile": "string",
  "volume": 1
}
```

### Subtitle

``` json
{
  "id": "uuid",
  "startTime": 0,
  "endTime": 0,
  "text": "string",
  "translatedText": "string",
  "language": "ar-EG",
  "speaker": "string",
  "style": {}
}
```

### Render job

``` json
{
  "id": "uuid",
  "projectId": "uuid",
  "status": "queued",
  "progress": 0,
  "format": "mp4",
  "resolution": "1080p",
  "frameRate": 30,
  "codec": "h264",
  "outputPath": "string",
  "error": null,
  "createdAt": "datetime",
  "completedAt": null
}
```

### AI provider

``` json
{
  "id": "uuid",
  "name": "string",
  "providerType": "cloud",
  "enabled": true,
  "capabilities": [],
  "models": [],
  "healthStatus": "unknown",
  "priority": 1,
  "configuration": {}
}
```

------------------------------------------------------------------------

## 04 --- Database tables

Create normalized tables as required by the implemented features:

-   `users`
-   `user_settings`
-   `projects`
-   `project_settings`
-   `media_assets`
-   `media_metadata`
-   `media_uploads`
-   `scenes`
-   `shots`
-   `keyframes`
-   `characters`
-   `character_references`
-   `character_appearances`
-   `environments`
-   `environment_references`
-   `timelines`
-   `timeline_tracks`
-   `timeline_clips`
-   `timeline_markers`
-   `timeline_transitions`
-   `timeline_effects`
-   `timeline_keyframes`
-   `editing_decisions`
-   `audio_tracks`
-   `audio_segments`
-   `speakers`
-   `voice_profiles`
-   `transcripts`
-   `translations`
-   `localizations`
-   `subtitles`
-   `subtitle_styles`
-   `shorts`
-   `chapters`
-   `render_jobs`
-   `render_outputs`
-   `render_presets`
-   `ai_providers`
-   `ai_models`
-   `provider_usage`
-   `engine_registry`
-   `engine_runs`
-   `pipeline_runs`
-   `pipeline_steps`
-   `job_queue`
-   `job_logs`
-   `quality_reports`
-   `project_versions`
-   `export_history`
-   `storage_records`
-   `notifications`
-   `audit_logs`

Database requirements:

-   UUID primary keys where appropriate.
-   Foreign-key relationships.
-   Index project IDs and frequently queried timestamps.
-   Transactions for multi-record operations.
-   Versioned migrations.
-   Input and data validation.
-   Backup and recovery procedures.
-   Persistent job status.
-   No destructive schema changes without a migration and recovery plan.
-   Create only tables used by real features; avoid unused schema
    scaffolding.

------------------------------------------------------------------------

## 05 --- API routes

Base path: `/api/v1`

### System

-   `GET /health`
-   `GET /system/status`
-   `GET /system/capabilities`

### Projects

-   `GET /projects`
-   `POST /projects`
-   `GET /projects/:id`
-   `PATCH /projects/:id`
-   `DELETE /projects/:id`
-   `POST /projects/:id/duplicate`

### Media

-   `POST /media/upload`
-   `GET /media`
-   `GET /media/:id`
-   `DELETE /media/:id`
-   `GET /media/:id/metadata`
-   `GET /media/:id/thumbnail`

### Analysis

-   `POST /analysis/:projectId/start`
-   `GET /analysis/:projectId/status`
-   `GET /analysis/:projectId/results`
-   `POST /analysis/:projectId/retry`

### Scenes

-   `GET /projects/:id/scenes`
-   `GET /scenes/:id`
-   `PATCH /scenes/:id`

### Editing

-   `POST /editing/:projectId/plan`
-   `POST /editing/:projectId/execute`
-   `GET /editing/:projectId/status`

### Timeline

-   `GET /projects/:id/timeline`
-   `PUT /projects/:id/timeline`
-   `POST /timeline/:id/clips`
-   `PATCH /clips/:id`
-   `DELETE /clips/:id`

### Characters

-   `GET /projects/:id/characters`
-   `POST /characters`
-   `PATCH /characters/:id`
-   `POST /characters/:id/references`
-   `GET /characters/:id/consistency`

### Environments

-   `GET /projects/:id/environments`
-   `POST /environments`
-   `GET /environments/:id/continuity`

### Audio

-   `POST /audio/analyze`
-   `POST /audio/enhance`
-   `POST /audio/mix`
-   `GET /audio/:id/status`

### Voice

-   `POST /voice/generate`
-   `GET /voice/profiles`
-   `POST /voice/profiles`

### Translation and localization

-   `POST /translation/detect`
-   `POST /translation/translate`
-   `POST /translation/validate`
-   `POST /localization/egyptian-arabic`
-   `POST /localization/custom`
-   `POST /localization/validate`

### Subtitles

-   `POST /subtitles/generate`
-   `POST /subtitles/translate`
-   `PATCH /subtitles/:id`
-   `GET /subtitles/:projectId/export`

### Shorts and long video

-   `POST /shorts/generate`
-   `GET /shorts/:projectId`
-   `GET /shorts/:id`
-   `POST /long-video/generate`
-   `GET /long-video/:projectId/status`

### Rendering and export

-   `POST /render/start`
-   `GET /render/jobs`
-   `GET /render/:id`
-   `POST /render/:id/cancel`
-   `POST /render/:id/retry`
-   `GET /exports`
-   `GET /exports/:id`
-   `POST /exports/:id/download`

### Providers

-   `GET /providers`
-   `POST /providers`
-   `PATCH /providers/:id`
-   `POST /providers/:id/test`
-   `GET /providers/:id/models`

All endpoints must implement suitable validation, standardized errors,
authorization and authentication where applicable. Long-running tasks
must return job identifiers and expose real status rather than keeping
an HTTP request open indefinitely.

------------------------------------------------------------------------

## 06 --- Complete automatic pipeline

1.  Receive uploaded video.
2.  Validate file and inspect metadata.
3.  Create project and media records.
4.  Extract audio and video streams.
5.  Generate thumbnails and representative frames.
6.  Analyze video content.
7.  Detect scenes and shots.
8.  Analyze narrative and events.
9.  Detect recurring characters.
10. Build character references.
11. Analyze environments.
12. Transcribe speech.
13. Identify speakers.
14. Analyze audio quality.
15. Generate editing decisions.
16. Construct an editable timeline.
17. Remove unnecessary pauses where appropriate.
18. Improve pacing and transitions.
19. Enhance audio.
20. Translate dialogue.
21. Localize dialogue into Egyptian Arabic by default.
22. Generate optional dubbed audio.
23. Generate subtitles.
24. Apply visual enhancements.
25. Perform color grading.
26. Generate long-form output.
27. Identify and generate independent Shorts.
28. Adapt outputs to requested aspect ratios.
29. Render outputs.
30. Run final quality control.
31. Store final outputs.
32. Display preview, export and download options.

Every pipeline step must track:

-   Status.
-   Progress.
-   Start and completion timestamps.
-   Retry count.
-   Error details.
-   Output references.
-   Execution logs.

The pipeline must support pause where possible, resume, retry,
cancellation, recovery, independent task execution, dependency tracking
and progress reporting.

Do not run dependent steps before prerequisites are complete. Persist
job state so a server restart does not silently lose a job.

------------------------------------------------------------------------

## 07 --- AI provider architecture

Implement a provider-independent architecture with:

-   Provider registry.
-   Provider manager.
-   Provider router.
-   Provider health checks.
-   Provider fallback.
-   Model registry.
-   Model selector.
-   Usage tracker.
-   Cost estimator.
-   Capability resolver.
-   Provider adapters.
-   Provider validation.

Provider categories:

1.  Large language models.
2.  Vision models.
3.  Speech recognition.
4.  Text-to-speech.
5.  Translation.
6.  Image generation.
7.  Video generation.
8.  Audio processing.
9.  Video enhancement.
10. Local open-source models.

Each provider declares:

-   `providerId`
-   `providerName`
-   `capabilities`
-   `supportedModels`
-   `authenticationMethod`
-   `rateLimits`
-   `maximumInput`
-   `maximumOutput`
-   `pricingMetadata`
-   `availability`
-   `healthStatus`

Requirements:

-   Multiple providers.
-   Capability-based routing.
-   Fallback routing.
-   Timeout management.
-   Rate-limit handling.
-   Error recovery.
-   Usage tracking.
-   Cost estimates.
-   Secure credentials.
-   Model availability verification.

Never assume an open-source model can run inside a browser or on the
user's phone. Heavy processing must use an appropriate server, cloud
worker or supported external service. Clearly distinguish a model that
is installed, configured, reachable and actually working.

------------------------------------------------------------------------

## 08 --- Video and audio formats

### Input video

-   MP4
-   MOV
-   MKV
-   WEBM
-   AVI
-   M4V

### Input audio

-   MP3
-   WAV
-   AAC
-   M4A
-   FLAC
-   OGG

### Output video

-   MP4
-   WEBM
-   MOV where supported

### Output audio

-   MP3
-   WAV
-   AAC

### Subtitle formats

-   SRT
-   VTT
-   ASS

### Aspect ratios

-   16:9
-   9:16
-   1:1
-   4:5
-   4:3
-   Custom

### Resolutions

-   480p
-   720p
-   1080p
-   1440p
-   2160p where supported

### Frame rates

-   24
-   25
-   30
-   50
-   60

Do not display or advertise an output option unless the active rendering
backend and encoder support it. Probe installed FFmpeg capabilities at
runtime.

------------------------------------------------------------------------

## 09 --- Video production profiles

Create editable profiles:

1.  Cinematic Film
2.  Documentary
3.  YouTube Long Form
4.  YouTube Shorts
5.  TikTok
6.  Instagram Reels
7.  Podcast
8.  Educational
9.  Commercial Advertisement
10. Anime Conversion
11. Storytelling
12. Professional Social Media

Each profile defines:

-   Aspect ratio.
-   Output resolution.
-   Frame rate.
-   Editing style.
-   Pacing.
-   Subtitle style.
-   Audio treatment.
-   Transition preferences.
-   Color grading.
-   Export preset.

Profiles must be editable, validated and saved per project or as
reusable user presets.

------------------------------------------------------------------------

## 10 --- Character and environment continuity

Create a project-level continuity database.

For each character, store:

-   Unique identifier.
-   Reference images.
-   Appearance description.
-   Clothing description.
-   Color characteristics.
-   Scene appearances.
-   Voice association.
-   Confidence scores.
-   Continuity warnings.

For each environment, store:

-   Location description.
-   Background references.
-   Lighting.
-   Color palette.
-   Object positions when detectable.
-   Scene appearances.
-   Continuity warnings.

Generate:

-   Character Consistency Report.
-   Environment Consistency Report.
-   Scene Continuity Report.

**Important:** Analysis and generative reconstruction are different
capabilities. Do not claim that a normal video editor can automatically
regenerate missing visual content. Use a compatible generative provider
only when configured and available. Preserve original source footage and
make generated replacements explicitly identifiable and reversible.

------------------------------------------------------------------------

## 11 --- Localization and Egyptian Arabic

Default target language: `ar-EG`

Localization modes:

-   Natural Egyptian Arabic.
-   Formal Arabic.
-   Gulf Arabic.
-   Levantine Arabic.
-   English.
-   Custom language and dialect.

Egyptian Arabic requirements:

-   Natural conversational phrasing.
-   Context preservation.
-   Correct terminology.
-   Speaker personality preservation.
-   Appropriate expressions.
-   Timing-aware dialogue.
-   Subtitle readability.
-   Natural voice generation when a TTS provider is configured.

Create translation memory. Maintain both source and target text. Allow
correction of translated segments. Never overwrite original transcripts.

------------------------------------------------------------------------

## 12 --- Complete user interface

### Main dashboard

-   New Project.
-   Upload Video.
-   Recent Projects.
-   Processing Jobs.
-   Completed Videos.
-   AI Engine Status.
-   Provider Status.
-   Storage Usage.
-   Production Statistics.

### Project workspace

-   Project Information.
-   Source Media.
-   Analysis.
-   Scenes.
-   Characters.
-   Environments.
-   Timeline.
-   Audio.
-   Subtitles.
-   Localization.
-   Shorts.
-   Long Video.
-   Render.
-   Export.

### Automatic Studio

-   Upload source.
-   Select production profile.
-   Select language.
-   Select output types.
-   Start automatic production.
-   Monitor pipeline.
-   Preview results.
-   Export.

### Advanced Editor

-   Video player.
-   Multi-track timeline.
-   Clip editing.
-   Audio mixer.
-   Subtitle editor.
-   Effects.
-   Color grading.
-   Keyframes.
-   Undo and redo.

### AI Control Center

-   Provider manager.
-   Model registry.
-   Capability matrix.
-   Provider health.
-   API configuration.
-   Usage.
-   Cost estimates.
-   Fallback configuration.

### Settings

-   Interface language.
-   Theme.
-   Default localization.
-   Default export.
-   Storage.
-   AI providers.
-   Performance.
-   Notifications.
-   Privacy.
-   Data retention.

Every screen needs loading, empty, error and success states. All
controls must perform real actions or be clearly marked as unavailable;
do not create decorative controls that imply nonexistent functionality.

------------------------------------------------------------------------

## 13 --- Design system

Visual direction: professional premium creative studio.

Default theme: dark.

  Token               Value
  ------------------- -----------
  Background          `#0B0D12`
  Primary surface     `#141923`
  Secondary surface   `#1C2431`
  Primary accent      `#7657F6`
  Secondary accent    `#27C7D9`
  Success             `#25B985`
  Warning             `#F0B64B`
  Error               `#EF5965`
  Text                `#F4F5F8`

Requirements:

-   Responsive desktop, tablet and Android-browser layouts.
-   RTL and LTR support.
-   Accessible controls and keyboard navigation.
-   Reusable components.
-   Clear loading, empty, error and notification states.
-   Timeline controls usable on narrow screens, with a practical mobile
    editing layout.

------------------------------------------------------------------------

## 14 --- Security and data management

Security requirements:

-   Never expose API keys in frontend code.
-   Use server-side environment variables or a secure secrets service.
-   Validate uploads.
-   Restrict file types and sizes.
-   Validate MIME types and actual media signatures.
-   Sanitize filenames.
-   Prevent path traversal.
-   Restrict API access.
-   Rate-limit sensitive endpoints.
-   Protect user data.
-   Apply access controls.
-   Log security events.
-   Encrypt sensitive credentials.
-   Provide deletion controls.

Storage requirements:

-   Original media.
-   Temporary processing files.
-   Extracted frames.
-   Audio files.
-   Thumbnails.
-   Project files.
-   Timeline versions.
-   Rendered outputs.
-   Export history.

Use configurable retention policies. Do not silently delete original
media. Provide clear storage usage and cleanup controls.

------------------------------------------------------------------------

## 15 --- Testing architecture

### Unit tests

-   Video analysis.
-   Scene detection.
-   Editing decisions.
-   Timeline operations.
-   Character tracking.
-   Environment tracking.
-   Audio processing.
-   Translation.
-   Localization.
-   Subtitle timing.
-   Shorts generation.
-   Rendering command generation.

### Integration tests

-   Upload to analysis.
-   Analysis to editing.
-   Editing to timeline.
-   Timeline to rendering.
-   Translation to dubbing.
-   Subtitles to export.
-   Provider fallback.
-   Storage recovery.

### End-to-end tests

-   Create project.
-   Upload a real test video.
-   Analyze video.
-   Generate edit plan.
-   Generate subtitles.
-   Localize.
-   Generate Shorts.
-   Render.
-   Export.

### Performance tests

-   Large video uploads.
-   Long-form processing.
-   Multiple render jobs.
-   Memory usage.
-   Worker recovery.
-   Concurrent requests.

### Security tests

-   Invalid uploads.
-   Unauthorized access.
-   Credential exposure.
-   File path manipulation.
-   API abuse.

Tests must use small fixtures where possible and must not depend on paid
provider calls unless explicitly configured as optional integration
tests.

------------------------------------------------------------------------

## 16 --- Performance and scalability

Implement where supported by the deployment environment:

-   Asynchronous processing.
-   Background workers.
-   Persistent job queues.
-   Chunked uploads.
-   Resumable uploads.
-   Frame sampling.
-   Thumbnail caching.
-   Media caching.
-   Streaming previews.
-   Render segmentation.
-   Resource monitoring.
-   Worker concurrency limits.
-   Retry policies.
-   Checkpoint recovery.

Avoid loading entire large videos into browser memory. Avoid blocking
the frontend during rendering. Use a persistent job queue when the
deployment environment supports it. Clearly communicate when the current
hosting platform cannot run background media workers.

------------------------------------------------------------------------

## 17 --- Environment configuration

Create or update `.env.example` with documented optional settings:

``` dotenv
NODE_ENV=development
PORT=3000
DATABASE_URL=
STORAGE_DRIVER=local
STORAGE_PATH=
TEMP_STORAGE_PATH=
MAX_UPLOAD_SIZE=
MAX_CONCURRENT_JOBS=
AI_PROVIDER=
AI_MODEL=
GEMINI_API_KEY=
OPENAI_API_KEY=
WHISPER_ENDPOINT=
TTS_ENDPOINT=
FFMPEG_PATH=
FFPROBE_PATH=
LOG_LEVEL=info
CORS_ORIGIN=
```

All credentials must remain server-side. Do not require every provider
to be configured. The application must explain which capabilities are
unavailable when providers are not configured. Never commit a real
`.env` file or API secret.

------------------------------------------------------------------------

## 18 --- Deployment architecture

Deployment components:

-   Frontend application.
-   Backend API.
-   Database.
-   Media storage.
-   Background workers.
-   AI provider adapters.
-   Rendering workers.
-   Monitoring.

Support development, production, Docker, cloud and local development
environments as appropriate.

The application must not assume that static frontend hosting can execute
FFmpeg or persistent background workers. If the existing deployment is
frontend-only, implement an appropriate backend integration without
breaking the current deployment. Document any external infrastructure
required for real video processing.

------------------------------------------------------------------------

## 19 --- Development phases

  Phase   Scope
  ------- ------------------------------------------------
  00      Repository inspection and architecture mapping
  01      Core architecture and configuration
  02      Database and persistent storage
  03      Media upload and management
  04      Video intelligence
  05      Scene detection and story intelligence
  06      Editing decision engine
  07      Automatic editing
  08      Timeline and editor
  09      Character and environment consistency
  10      Audio intelligence and processing
  11      Voice Studio
  12      Translation and localization
  13      Subtitle engine
  14      Visual effects and color grading
  15      Video enhancement
  16      Shorts generation
  17      Long video generation
  18      Rendering engine
  19      Quality control
  20      Export and delivery
  21      Performance and security
  22      Production deployment

Each phase must be independently tested. Do not skip phases without
validating dependencies. Update the project documentation and
implementation status after each phase.

------------------------------------------------------------------------

## 20 --- Existing project preservation

Before making changes:

1.  Inspect every existing source directory.
2.  Inspect existing package dependencies and scripts.
3.  Inspect current routes.
4.  Inspect existing UI components.
5.  Inspect existing services.
6.  Inspect the existing orchestrator.
7.  Inspect existing AI provider integrations.
8.  Inspect all existing tests.
9.  Identify completed functionality.
10. Identify incomplete functionality.

Known examples from the current project history include:

-   `AutomaticPipelineTracker.tsx`
-   `StudioWorkspace.tsx`
-   `App.tsx`
-   `main.tsx`
-   `vite.config.ts`
-   `package.json`
-   Existing orchestrator modules and tests.

These are examples, not a complete inventory.

For every target file classify it as:

-   `EXISTS_AND_WORKS`
-   `EXISTS_NEEDS_UPGRADE`
-   `MISSING`
-   `DUPLICATE`
-   `NOT_APPLICABLE`

Create an existing-to-target compatibility map. Reuse working
implementations. Do not remove existing features. Do not duplicate
services or orchestrators. Do not overwrite configuration files merely
because this blueprint contains a similarly named file.

------------------------------------------------------------------------

## 21 --- Implementation quality rules

Every implemented feature must have:

-   Actual implementation.
-   Defined inputs.
-   Defined outputs.
-   Validation.
-   Error handling.
-   Logging.
-   Tests.
-   Documentation.
-   UI integration where required.

Prohibited implementation shortcuts:

-   Fake functionality.
-   Empty placeholder modules marked complete.
-   Simulated video rendering presented as real rendering.
-   Fake AI results.
-   Hardcoded success states.
-   Broken imports.
-   Duplicate services.
-   Unnecessary dependencies.
-   Destructive migrations.
-   Unverified provider capabilities.
-   Exposed API credentials.

All progress indicators must reflect actual processing state. A
capability must be labelled unavailable, experimental or
provider-dependent when it is not fully operational.

------------------------------------------------------------------------

## 22 --- Final acceptance criteria

The application must be able to:

1.  Create a project.
2.  Upload a real video.
3.  Validate media.
4.  Extract metadata.
5.  Analyze scenes.
6.  Understand video content.
7.  Analyze narrative structure.
8.  Generate an editing plan.
9.  Build an editable timeline.
10. Perform actual automatic edits.
11. Analyze character consistency.
12. Analyze environment continuity.
13. Process audio.
14. Transcribe dialogue.
15. Translate dialogue.
16. Localize into Egyptian Arabic.
17. Generate dubbed audio when configured.
18. Generate subtitles.
19. Apply effects.
20. Apply color grading.
21. Enhance video when a compatible engine exists.
22. Generate multiple Shorts.
23. Produce long-form edits.
24. Render real video files.
25. Validate final outputs.
26. Export completed projects.

The application must also recover failed jobs, preserve original files,
support multiple projects and output profiles, display accurate
progress, report errors clearly, preserve project history and work on
Android and desktop browsers.

Acceptance must be based on tests and actual output files, not UI
appearance alone.

------------------------------------------------------------------------

## 23 --- Final execution instructions for Google AI Studio

**START BY INSPECTING THE EXISTING REPOSITORY.**

Do not create a new project.\
Do not delete existing files.\
Do not replace working code.\
Do not generate hundreds of empty files.

First produce:

1.  Complete existing file inventory.
2.  Complete target file tree.
3.  Existing-to-target mapping.
4.  Missing files report.
5.  Duplicate files report.
6.  Dependency compatibility report.
7.  Implementation plan.
8.  Testing plan.

Then begin implementation incrementally.

Preserve all existing functionality. Implement real production
capabilities. Run the available test suite after every phase. Run the
production build. Fix regressions. Report exact files created, updated
and preserved. Report actual test results and remaining limitations.

Never report a feature as completed unless it is implemented and
verified.

### Final product vision

A professional global AI video production platform:

-   One video upload.
-   Automatic video understanding.
-   Automatic professional editing.
-   Character and environment continuity analysis.
-   Audio enhancement.
-   Multilingual localization.
-   Egyptian Arabic dubbing when configured.
-   Automatic subtitles.
-   Long-form video production.
-   Short-form video production.
-   Real video rendering.
-   Quality control.
-   Final export.

------------------------------------------------------------------------

**END OF MASTER PROJECT SPECIFICATION**
