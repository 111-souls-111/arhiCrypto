```uml
@startuml Controllers
!theme plain
skinparam classAttributeIconSize 0

package "controller" #BBDEFB {
  
  class AuthController {
    --
    + register(RegisterRequest) : ResponseEntity<AuthResponse>
    + login(LoginRequest) : ResponseEntity<AuthResponse>
    + refreshToken(String) : ResponseEntity<AuthResponse>
    + logout() : ResponseEntity<Void>
  }
  
  class UserController {
    --
    + getCurrentUser() : ResponseEntity<UserDTO>
    + updateProfile(UserDTO) : ResponseEntity<UserDTO>
    + deleteAccount() : ResponseEntity<Void>
  }
  
  class MarketController {
    --
    + getAllCoins() : ResponseEntity<List<CoinDTO>>
    + getCoin(String) : ResponseEntity<CoinDTO>
    + getTrending() : ResponseEntity<List<CoinDTO>>
    + getHistory(String, Period) : ResponseEntity<List<PriceHistoryDTO>>
  }
  
  class PortfolioController {
    --
    + getPortfolio(Long) : ResponseEntity<PortfolioDTO>
    + getBalance(Long) : ResponseEntity<BalanceDTO>
    + getProfitLoss(Long) : ResponseEntity<ProfitLossDTO>
  }
  
  class TradeController {
    --
    + executeTrade(TradeRequestDTO) : ResponseEntity<TradeResponseDTO>
    + getHistory(Long) : ResponseEntity<List<TradeDTO>>
    + cancelTrade(Long) : ResponseEntity<Void>
  }
  
  class OrderController {
    --
    + createOrder(OrderRequestDTO) : ResponseEntity<OrderDTO>
    + getOpenOrders(Long) : ResponseEntity<List<OrderDTO>>
    + cancelOrder(Long) : ResponseEntity<Void>
  }
  
  class PredictionController {
    --
    + predict(String, PredictionModel) : ResponseEntity<PredictionDTO>
    + getPredictions(String) : ResponseEntity<List<PredictionDTO>>
    + getAccuracy() : ResponseEntity<Map<PredictionModel, Double>>
  }
}

@enduml
```
