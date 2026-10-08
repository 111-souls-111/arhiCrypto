@startuml Crypto Trading Backend - Overview
!theme plain
skinparam classAttributeIconSize 0

package "Controllers" {
  class AuthController
  class UserController
  class MarketController
  class PortfolioController
  class TradeController
}

package "Services" {
  interface AuthService
  interface UserService
  interface MarketService
  interface PortfolioService
  interface TradeService
  interface PriceService
}

package "Repositories" {
  interface UserRepository
  interface CoinRepository
  interface PortfolioRepository
  interface TradeRepository
  interface OrderRepository
}

package "Entities" {
  class User
  class Coin
  class Portfolio
  class PortfolioItem
  class Trade
  class Order
}

package "DTOs" {
  class UserDTO
  class TradeRequestDTO
  class TradeResponseDTO
  class MarketDataDTO
}

Controllers ..> Services : uses
Services ..> Repositories : uses
Repositories ..> Entities : manages
Controllers ..> DTOs : uses

@enduml
