# Credits

**DD-MB** (Dopravní deník – Moduly Brno) is a Computer-Assisted Train Notification system for modular model railroad operations.

---

## Open-Source Libraries

### Backend (`src/backend`)

| Package | License | Description |
| --- | --- | --- |
| [express](https://expressjs.com/) | MIT | Fast, minimalist web framework for Node.js |
| [socket.io](https://socket.io/) | MIT | Real-time bidirectional event-based communication |
| [adm-zip](https://github.com/cthackers/adm-zip) | MIT | ZIP file reading/writing for layout import |
| [bcryptjs](https://github.com/dcodeIO/bcrypt.js) | MIT | Password hashing for authentication |
| [cors](https://github.com/expressjs/cors) | MIT | Cross-Origin Resource Sharing middleware |
| [dotenv](https://github.com/motdotla/dotenv) | BSD-2-Clause | Environment variable loading from `.env` files |
| [express-session](https://github.com/expressjs/session) | MIT | Session middleware for Express |
| [multer](https://github.com/expressjs/multer) | MIT | Multipart/form-data handling for file uploads |
| [uuid](https://github.com/uuidjs/uuid) | MIT | RFC-compliant UUID generation |
| [socket.io-client](https://socket.io/) *(dev)* | MIT | Socket.IO client used in unit tests |

### Frontend (`src/frontend`)

| Package | License | Description |
| --- | --- | --- |
| [react](https://react.dev/) | MIT | UI library for building component-based interfaces |
| [react-dom](https://react.dev/) | MIT | DOM rendering for React |
| [socket.io-client](https://socket.io/) | MIT | Real-time communication with the backend |
| [lucide-react](https://lucide.dev/) | ISC | Clean, consistent icon set for React |
| [vite](https://vitejs.dev/) *(dev)* | MIT | Fast frontend build tool and dev server |
| [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react) *(dev)* | MIT | React Fast Refresh and JSX transform for Vite |
| [tailwindcss](https://tailwindcss.com/) *(dev)* | MIT | Utility-first CSS framework |
| [@tailwindcss/postcss](https://tailwindcss.com/) *(dev)* | MIT | PostCSS integration for Tailwind CSS v4 |
| [postcss](https://postcss.org/) *(dev)* | MIT | CSS transformation tool |
| [autoprefixer](https://github.com/postcss/autoprefixer) *(dev)* | MIT | Automatic vendor prefix handling |
| [@types/react](https://github.com/DefinitelyTyped/DefinitelyTyped) *(dev)* | MIT | TypeScript type definitions for React |
| [@types/react-dom](https://github.com/DefinitelyTyped/DefinitelyTyped) *(dev)* | MIT | TypeScript type definitions for React DOM |

### Testing

| Package | License | Description |
| --- | --- | --- |
| [@playwright/test](https://playwright.dev/) | Apache-2.0 | End-to-end browser testing framework |

### Runtime

| Software | License | Description |
| --- | --- | --- |
| [Node.js](https://nodejs.org/) | MIT | JavaScript runtime (v20.19+ or v22.12+ required) |

---

## Audio

Notification and alert sounds used in this application:

| File | Title | Author | Source | License |
| --- | --- | --- | --- | --- |
| `Default Alert1.mp3` | MessageAlert02.wav | aj_heels | [https://freesound.org/people/aj_heels/sounds/634084/](https://freesound.org/people/aj_heels/sounds/634084/) | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) |
| `Default Alert2.mp3` | Vintage Alert Notification 2_2 | Joao_Janz | [https://freesound.org/people/Joao_Janz/sounds/504861/](https://freesound.org/people/Joao_Janz/sounds/504861/) | [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) |
| `Default Alert3.mp3` | up3.mp3 | stwime | [https://freesound.org/people/stwime/sounds/545373/](https://freesound.org/people/stwime/sounds/545373/) | [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) |
| `Default Alert4.mp3` | 14. Larry Phone Notif | AlixTwix6 | [https://freesound.org/people/AlixTwix6/sounds/800529/](https://freesound.org/people/AlixTwix6/sounds/800529/) | [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/) |
| `Default Alert5.mp3` | 320655__rhodesmas__level-up-01.mp3 | shinephoenixstormcrow | [https://freesound.org/people/shinephoenixstormcrow/sounds/337049/](https://freesound.org/people/shinephoenixstormcrow/sounds/337049/) | [CC BY 3.0](https://creativecommons.org/licenses/by/3.0/) |
| `Default Alert6.mp3` | 3attention signal tone | bowlingballout | [https://freesound.org/people/bowlingballout/sounds/764857/](https://freesound.org/people/bowlingballout/sounds/764857/) | [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) |

> **Note for contributors:** If you add custom audio files to the `public/sounds/` directory, please add an entry to this table with the original title, author, source URL, and license.

---

## Acknowledgements

DD-MB was built for the modular model railroad community in the Czech Republic (CATN – Computer-Assisted Train Notification). The timetable import format is based on CSV exports used at modular model railroad events in Central Europe.

---

*All trademarks are property of their respective owners.*
