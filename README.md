# Game Hub Backend Application

#Created By: Script Squad

## Project Overview
A comprehensive backend for a web-based game platform featuring:
- User Authentication
- Multiple Game Modes
- Real-time Game Tracking
- Multiplayer Interactions
- Payment Integration (M-Pesa)

## Features

### Authentication
- User Registration
- Secure Login with JWT
- Profile Management

### Game Modes
1. **Spin and Win** (Single Player)
   - Random reward generation
   - Instant play mechanics
   - Bet tracking

2. **Russian Roulette** (Multiplayer)
   - 2-player competitive game
   - Real-time game progression
   - Betting system
   - Survival/Elimination betting

### Financial Management
- Balance Deposits
- Withdrawals
- M-Pesa Integration
- Transaction Tracking

## Tech Stack
- Backend: Flask
- Database: PostgreSQL
- ORM: SQLAlchemy
- Authentication: Flask-JWT
- Payment: M-Pesa API
- Real-time Events: Server-Sent Events (SSE)

## Database Models
- User
- Transaction
- Game
- GameSession
- SpinAndWin
- Multiplayer
- RussianRoulette
- BetHistory

## Key Endpoints

### Authentication
- `POST /register`: User registration
- `POST /login`: User login
- `GET /profile`: User profile details

### Financial Routes
- `POST /deposit`: Add funds via M-Pesa
- `POST /withdraw`: Withdraw funds

### Game Routes
- `POST /games/spin-and-win/play`: Play Spin and Win
- `POST /games/join`: Join multiplayer game
- `POST /games/place-bet`: Place bet in Russian Roulette
- `POST /games/pull-trigger`: Pull trigger in Russian Roulette
- `POST /games/leave`: Leave current game

### User Statistics
- `GET /history`: Game bet history
- `GET /stats`: Overall and per-game statistics

## Real-time Communication
- Server-Sent Events (SSE) for game updates
- Broadcast game status
- Real-time player notifications

## M-Pesa Integration
### Deposit Flow
1. Initiate M-Pesa payment request
2. Receive STK push callback
3. Confirm transaction
4. Update user balance

### Withdrawal Flow
1. Verify user balance
2. Initiate M-Pesa withdrawal
3. Process transaction
4. Update user balance

## Environment Setup

### Prerequisites
- Python 3.8+
- PostgreSQL
- M-Pesa Developer Account

### Installation Steps
1. Clone repository
2. Create virtual environment
3. Install dependencies
   ```bash
   pip install -r requirements.txt
   ```
4. Configure `.env` file
   ```
   DB_USER=your_username
   DB_PASSWORD=your_password
   DB_HOST=localhost
   DB_PORT=5432
   DB_NAME=game_hub
   JWT_SECRET_KEY=your_secret_key
   MPESA_CONSUMER_KEY=your_mpesa_key
   MPESA_CONSUMER_SECRET=your_mpesa_secret
   ```
5. Run database migrations
   ```bash
   flask db upgrade
   ```
6. Start application
   ```bash
   flask run
   ```

## Security Features
- Password hashing
- JWT authentication
- Input validation
- Secure transaction processing

## Error Handling
- Comprehensive error responses
- Logging of critical errors
- Graceful error management

## Scaling Considerations
- Stateless authentication
- Efficient database queries
- Event-driven architecture

## Monitoring & Logging
- Application performance tracking
- Transaction audit logs
- Error reporting

## Deployment
- Gunicorn/uWSGI 
- NGINX reverse proxy
- Environment-specific configurations

## Future Roadmap
- More game modes
- Advanced matchmaking
- Social features
- Enhanced reporting

## Contributing
1. Fork repository
2. Create feature branch
3. Commit changes
4. Submit pull request

## License
MIT License
Copyright (c) 2025 Marilyn

## Contact
https://github.com/Marilynmonroecode/game_hub_backend

### Troubleshooting
- Verify database connections
- Check M-Pesa API credentials
- Review JWT configuration
- Monitor SSE connections

## Disclaimer
Ensure compliance with local gambling regulations and obtain necessary licenses before deployment.
