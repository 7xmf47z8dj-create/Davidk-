 MANUAL DE DESARROLLO - BOT DE TRADING MEMCOINS SOLANA  
  
## Sistema Completo de Trading en Pump.fun con Telegram en Rust para Pop!_OS  
  
```  
VERSIÓN: 1.0  
ÚLTIMA ACTUALIZACIÓN: Febrero 2026  
IDIOMA: Español  
TARGET: Pop!_OS 22.04 / Ubuntu 22.04+  
BLOCKCHAIN: Solana Mainnet  
STACK: Rust + Solana SDK + Helius + Pump.fun + Telegram  
PROPÓSITO: Manual de instrucciones para Gemini AI  
```  
  
-----  
  
## 📋 INSTRUCCIONES DE USO DE ESTE MANUAL  
  
**Para Gemini AI:**  
  
Este es tu manual de referencia completo para crear un bot de trading de memcoins en Solana. Al recibir una solicitud para generar este proyecto:  
  
1. **LEE ESTE MANUAL COMPLETO** antes de generar cualquier código  
1. **SIGUE EXACTAMENTE** el formato de salida especificado  
1. **VERIFICA** todas las URLs y versiones antes de generar  
1. **INCLUYE** todos los comandos gedit para cada archivo  
1. **GENERA** código funcional para trading REAL en mainnet  
1. **DOCUMENTA** todo en español  
  
**Formato de invocación del usuario:**  
  
```  
"Lee el manual MANUAL_SOLANA_MEMECOIN_BOT.md desde mi Google Drive y genera   
el proyecto completo de bot de trading de memcoins en Solana siguiendo todas   
las especificaciones"  
```  
  
-----  
  
## 📋 ÍNDICE DE CONTENIDOS  
  
1. [Arquitectura del Sistema](#arquitectura)  
1. [Reglas Generales de Generación](#reglas-generales)  
1. [Formato de Salida Obligatorio](#formato-salida)  
1. [Estructura del Proyecto](#estructura-proyecto)  
1. [Especificaciones Técnicas](#especificaciones-tecnicas)  
1. [Módulos del Sistema](#modulos-sistema)  
1. [Integración con APIs](#integracion-apis)  
1. [Trading en Pump.fun](#pump-fun)  
1. [Sistema de Propinas con Helius](#helius-tips)  
1. [Deployment y Scripts](#deployment-scripts)  
1. [Testing y Seguridad](#testing-seguridad)  
1. [Checklist Final](#checklist-final)  
  
-----  
  
## 🏗️ ARQUITECTURA DEL SISTEMA {#arquitectura}  
  
### Flujo General del Bot  
  
```  
Usuario (Telegram)  
    │  
    ▼  
Bot de Telegram ←→ Módulo de Comandos  
    │                  │  
    **├─────────────────┼─────────────────┐**  
    ▼                 ▼                 ▼  
Monitor de       Trading            Análisis  
Tokens           Engine             de Mercado  
    │                 │                 │  
    ▼                 ▼                 ▼  
Dexscreener      Pump.fun API      GMGN API  
GMGN API         Helius RPC        Dexscreener  
    │                 │                 │  
    **└────────┬────────┴────────┬────────┘**  
             ▼                 ▼  
        Solana Mainnet ←→ Helius RPC  
         (Transacciones reales)  
```  
  
### Componentes Principales  
  
```  
solana_memecoin_bot/  
│  
**├──** Wallet Management      # Manejo de wallet SOL  
**├──** Pump.fun Integration   # API de pump.fun  
**├──** Helius Integration     # RPC + Propinas  
**├──** Dexscreener Monitor    # Seguimiento de tokens  
**├──** GMGN Integration       # Datos de mercado  
**├──** Trading Engine         # Compra/Venta  
**├──** Risk Management        # Gestión de riesgo  
**├──** Telegram Interface     # Control del usuario  
**└──** Alert System           # Notificaciones  
```  
  
-----  
  
## 📌 REGLAS GENERALES DE GENERACIÓN {#reglas-generales}  
  
### Regla 1: Seguridad es CRÍTICA  
  
**ANTES de generar cualquier código:**  
  
```  
⚠️  Este bot maneja DINERO REAL en Solana Mainnet  
⚠️  Los errores pueden resultar en PÉRDIDA DE FONDOS  
⚠️  La seguridad NO es opcional  
```  
  
**Requisitos de seguridad OBLIGATORIOS:**  
  
- ✅ Private keys NUNCA en código  
- ✅ Usar variables de entorno para credenciales  
- ✅ Validación de todas las transacciones  
- ✅ Límites de cantidad por operación  
- ✅ Confirmación del usuario para trades  
- ✅ Logging de todas las operaciones  
- ✅ Manejo de errores exhaustivo  
- ✅ Slippage control  
  
### Regla 2: Verificación Previa Obligatoria  
  
**ANTES de generar cualquier código, DEBES:**  
  
```  
✅ BUSCAR en crates.io las versiones más recientes  
✅ CONSULTAR docs.rs para sintaxis actual  
✅ VERIFICAR Solana SDK actual (solana-sdk, solana-client)  
✅ CONFIRMAR APIs de Pump.fun, Helius, Dexscreener, GMGN  
✅ VALIDAR que todo funciona en Mainnet  
```  
  
**Enlaces de Verificación Obligatorios:**  
  
- https://crates.io/ (versiones de crates)  
- https://docs.rs/ (documentación de crates)  
- https://docs.solana.com/ (documentación de Solana)  
- https://pump.fun/docs (API de pump.fun)  
- https://docs.helius.dev/ (Helius API)  
- https://docs.dexscreener.com/ (Dexscreener API)  
- https://gmgn.ai/ (GMGN)  
- https://core.telegram.org/bots/api (Telegram Bot API)  
  
### Regla 3: Formato de Salida Estandarizado  
  
**Para CADA archivo que generes, DEBES usar este formato EXACTO:**  
  
```  
**═══════════════════════════════════════════════════════**  
📄 ARCHIVO: [ruta/completa/del/archivo]  
**═══════════════════════════════════════════════════════**  
  
📂 Preparación:  
```bash  
mkdir -p [directorio/necesario]  
cd [directorio]  
```  
  
✏️ Comando gedit para abrir:  
  
```bash  
gedit [ruta/completa/archivo]  
```  
  
💾 Contenido del archivo:  
  
```rust  
[CÓDIGO COMPLETO AQUÍ]  
```  
  
✅ Verificación inmediata:  
  
```bash  
[comando para verificar que funciona]  
```  
  
🔗 Referencias importantes:  
  
- [link 1 a documentación relevante]  
- [link 2 a ejemplos]  
  
💡 Notas de seguridad:  
  
- ⚠️ [punto de seguridad crítico]  
- 💰 [consideración financiera]  
  
⚠️ Errores comunes a evitar:  
  
- ❌ [error común 1]  
- ✅ [cómo hacerlo correctamente]  
  
**═══════════════════════════════════════════════════════**  
  
```  
### Regla 4: Código Funcional y Seguro  
  
**Todo el código que generes DEBE:**  
  
- ✅ Compilar sin errores: `cargo check` pasa  
- ✅ Sin warnings críticos: `cargo clippy` limpio  
- ✅ Con tests: `cargo test` exitoso  
- ✅ Manejo de errores exhaustivo  
- ✅ Validación de inputs  
- ✅ Logging completo con tracing  
- ✅ Funcionar en Solana MAINNET  
- ✅ Documentado en español  
  
---  
  
## 🎯 FORMATO DE SALIDA OBLIGATORIO {#formato-salida}  
  
### Comandos gedit Maestros  
  
**Al inicio de cada fase, proporciona:**  
  
```bash  
# Abrir todos los archivos relacionados en pestañas de gedit:  
gedit archivo1.rs archivo2.rs archivo3.toml archivo4.sh  
  
# Esto permite al usuario editar múltiples archivos simultáneamente  
```  
  
-----  
  
## 🏗️ ESTRUCTURA DEL PROYECTO {#estructura-proyecto}  
  
### Árbol de Directorios Completo  
  
```  
solana_memecoin_bot/  
│  
**├──** 📄 Cargo.toml                    # Dependencias Solana  
**├──** 📄 .env.example                  # Plantilla de config  
**├──** 📄 .env                          # Config real (NUNCA versionar)  
**├──** 📄 .gitignore                    # Git ignore  
**├──** 📄 README.md                     # Documentación  
**├──** 📄 SECURITY.md                   # Guía de seguridad  
**├──** 📄 solana-memecoin-bot.service  # Systemd service  
│  
**├──** 📁 src/  
│   **├──** 📄 main.rs                   # Entry point  
│   **├──** 📄 config.rs                 # Configuración  
│   │  
│   **├──** 📁 wallet/                   # Gestión de wallet  
│   │   **├──** 📄 mod.rs  
│   │   **├──** 📄 keypair.rs            # Manejo de keys  
│   │   **└──** 📄 balance.rs            # Balance SOL/tokens  
│   │  
│   **├──** 📁 solana/                   # Interacción Solana  
│   │   **├──** 📄 mod.rs  
│   │   **├──** 📄 client.rs             # Cliente RPC  
│   │   **├──** 📄 transaction.rs        # Construcción TX  
│   │   **└──** 📄 confirmation.rs       # Confirmación TX  
│   │  
│   **├──** 📁 pumpfun/                  # Pump.fun integration  
│   │   **├──** 📄 mod.rs  
│   │   **├──** 📄 api.rs                # API client  
│   │   **├──** 📄 buy.rs                # Comprar tokens  
│   │   **├──** 📄 sell.rs               # Vender tokens  
│   │   **└──** 📄 pool.rs               # Info de pools  
│   │  
│   **├──** 📁 helius/                   # Helius integration  
│   │   **├──** 📄 mod.rs  
│   │   **├──** 📄 client.rs             # RPC client  
│   │   **├──** 📄 priority_fees.rs      # Propinas  
│   │   **└──** 📄 webhook.rs            # Webhooks  
│   │  
│   **├──** 📁 dexscreener/              # Dexscreener  
│   │   **├──** 📄 mod.rs  
│   │   **├──** 📄 api.rs                # API client  
│   │   **├──** 📄 monitor.rs            # Monitor tokens  
│   │   **└──** 📄 parser.rs             # Parse data  
│   │  
│   **├──** 📁 gmgn/                     # GMGN integration  
│   │   **├──** 📄 mod.rs  
│   │   **├──** 📄 api.rs                # API client  
│   │   **└──** 📄 analytics.rs          # Análisis  
│   │  
│   **├──** 📁 trading/                  # Trading engine  
│   │   **├──** 📄 mod.rs  
│   │   **├──** 📄 engine.rs             # Motor principal  
│   │   **├──** 📄 strategy.rs           # Estrategias  
│   │   **├──** 📄 risk.rs               # Gestión riesgo  
│   │   **└──** 📄 position.rs           # Posiciones  
│   │  
│   **├──** 📁 telegram/                 # Telegram bot  
│   │   **├──** 📄 mod.rs  
│   │   **├──** 📄 bot.rs                # Bot principal  
│   │   **├──** 📄 commands.rs           # Comandos  
│   │   **├──** 📄 callbacks.rs          # Botones  
│   │   **└──** 📄 alerts.rs             # Alertas  
│   │  
│   **└──** 📁 utils/                    # Utilidades  
│       **├──** 📄 mod.rs  
│       **├──** 📄 logger.rs             # Logging  
│       **└──** 📄 errors.rs             # Custom errors  
│  
**├──** 📁 scripts/                      # Scripts  
│   **├──** 📄 install.sh  
│   **├──** 📄 backup_wallet.sh  
│   **└──** 📄 check_balance.sh  
│  
**└──** 📁 tests/                        # Tests  
    **├──** 📄 integration_test.rs  
    **└──** 📄 trading_test.rs  
```  
  
-----  
  
## ⚙️ ESPECIFICACIONES TÉCNICAS {#especificaciones-tecnicas}  
  
### Cargo.toml - Dependencias Solana  
  
**VERIFICAR todas las versiones en https://crates.io/**  
  
```toml  
[package]  
name = "THE MONEY MACHINE"  
version = "0.1.0"  
edition = "2021"  
authors = ["David Abad"]  
description = "Bot de trading de memcoins en Solana"  
license = "MIT"  
  
[dependencies]  
# Solana SDK - VERIFICAR VERSION ACTUAL  
solana-sdk = "1.18"  
solana-client = "1.18"  
solana-transaction-status = "1.18"  
  
# Bot de Telegram - VERIFICAR VERSION  
teloxide = { version = "0.12", features = ["macros"] }  
  
# Async runtime - VERIFICAR VERSION  
tokio = { version = "1", features = ["full"] }  
  
# HTTP client - VERIFICAR VERSION  
reqwest = { version = "0.11", features = ["json"] }  
  
# Serialización - VERIFICAR VERSION  
serde = { version = "1.0", features = ["derive"] }  
serde_json = "1.0"  
  
# Anchor (para interactuar con programas)  
anchor-client = "0.29"  
anchor-lang = "0.29"  
  
# SPL Token  
spl-token = "4.0"  
spl-associated-token-account = "2.0"  
  
# Base58 encoding  
bs58 = "0.5"  
  
# Decimal math  
rust_decimal = "1.33"  
rust_decimal_macros = "1.33"  
  
# Logging  
tracing = "0.1"  
tracing-subscriber = "0.3"  
  
# Config  
dotenv = "0.15"  
  
# Error handling  
thiserror = "1.0"  
anyhow = "1.0"  
  
# Crypto  
ed25519-dalek = "2.0"  
  
# Time  
chrono = "0.4"  
  
[dev-dependencies]  
mockito = "1.0"  
  
[profile.release]  
opt-level = 3  
lto = true  
codegen-units = 1  
strip = true  
```  
  
### .env.example - Variables de Entorno  
  
```bash  
# **══════════════════════════════════════════════════════**  
# CONFIGURACIÓN DE WALLET SOLANA  
# **══════════════════════════════════════════════════════**  
  
# Private key de la wallet (base58)  
# ⚠️ NUNCA compartir esta clave  
# ⚠️ Usar wallet separada solo para el bot  
# Obtener con: solana-keygen new  
SOLANA_PRIVATE_KEY=tu_private_key_base58_aqui  
  
# Public key (address) de la wallet  
SOLANA_PUBLIC_KEY=tu_public_key_aqui  
  
# **══════════════════════════════════════════════════════**  
# CONFIGURACIÓN DE HELIUS RPC  
# **══════════════════════════════════════════════════════**  
  
# API Key de Helius (obtener en https://helius.dev)  
HELIUS_API_KEY=tu_helius_api_key_aqui  
  
# RPC URL de Helius (mainnet)  
HELIUS_RPC_URL=https://mainnet.helius-rpc.com/?api-key=<API_KEY>  
  
# **══════════════════════════════════════════════════════**  
# CONFIGURACIÓN DE TELEGRAM  
# **══════════════════════════════════════════════════════**  
  
# Token del bot (obtener de @BotFather)  
TELOXIDE_TOKEN=tu_telegram_token_aqui  
  
# Chat ID autorizado (solo este chat puede usar el bot)  
AUTHORIZED_CHAT_ID=tu_chat_id_aqui  
  
# **══════════════════════════════════════════════════════**  
# CONFIGURACIÓN DE DEXSCREENER  
# **══════════════════════════════════════════════════════**  
  
# API de Dexscreener (pública, no requiere key)  
DEXSCREENER_API_URL=https://api.dexscreener.com/latest  
  
# **══════════════════════════════════════════════════════**  
# CONFIGURACIÓN DE GMGN  
# **══════════════════════════════════════════════════════**  
  
# API de GMGN  
GMGN_API_URL=https://gmgn.ai/api  
  
# **══════════════════════════════════════════════════════**  
# CONFIGURACIÓN DE PUMP.FUN  
# **══════════════════════════════════════════════════════**  
  
# Program ID de pump.fun en Solana  
PUMPFUN_PROGRAM_ID=6EF8rrecthR5Dkzon8Nwu78hRvfCKubJ14M5uBEwF6P  
  
# API de pump.fun (si existe)  
PUMPFUN_API_URL=https://pumpportal.fun/api  
  
# **══════════════════════════════════════════════════════**  
# CONFIGURACIÓN DE TRADING  
# **══════════════════════════════════════════════════════**  
  
# Cantidad máxima de SOL por operación  
MAX_SOL_PER_TRADE=0.1  
  
# Slippage máximo permitido (en porcentaje)  
MAX_SLIPPAGE_PERCENT=5.0  
  
# Propina mínima para prioridad (en lamports)  
MIN_PRIORITY_FEE=10000  
  
# Propina máxima para prioridad (en lamports)  
MAX_PRIORITY_FEE=1000000  
  
# Stop loss automático (porcentaje)  
AUTO_STOP_LOSS_PERCENT=20.0  
  
# Take profit automático (porcentaje)  
AUTO_TAKE_PROFIT_PERCENT=50.0  
  
# **══════════════════════════════════════════════════════**  
# CONFIGURACIÓN DE SISTEMA  
# **══════════════════════════════════════════════════════**  
  
# Nivel de logs: trace, debug, info, warn, error  
RUST_LOG=info  
  
# Backtrace  
RUST_BACKTRACE=1  
  
# Network (mainnet-beta, devnet, testnet)  
SOLANA_NETWORK=mainnet-beta  
```  
  
-----  
  
## 📦 MÓDULOS DEL SISTEMA {#modulos-sistema}  
  
### Módulo 1: wallet/keypair.rs  
  
**Propósito:** Manejo seguro de private keys y wallet  
  
**Responsabilidades:**  
  
- Cargar keypair desde env  
- Validar keys  
- Firmar transacciones  
- NUNCA exponer private key  
  
**Estructura principal:**  
  
```rust  
use solana_sdk::signature::{Keypair, Signer};  
use bs58;  
use anyhow::{Result, Context};  
  
pub struct WalletManager {  
    keypair: Keypair,  
    pubkey: solana_sdk::pubkey::Pubkey,  
}  
  
impl WalletManager {  
    /// Carga la wallet desde variable de entorno  
    /// ⚠️ CRÍTICO: Valida que la key sea correcta  
    pub fn from_env() -> Result<Self> {  
        let private_key = std::env::var("SOLANA_PRIVATE_KEY")  
            .context("SOLANA_PRIVATE_KEY no encontrada")?;  
          
        // Decodificar base58  
        let bytes = bs58::decode(&private_key)  
            .into_vec()  
            .context("Private key inválida (base58)")?;  
          
        // Crear keypair  
        let keypair = Keypair::from_bytes(&bytes)  
            .context("No se pudo crear keypair")?;  
          
        let pubkey = keypair.pubkey();  
          
        tracing::info!("✅ Wallet cargada: {}", pubkey);  
          
        Ok(Self { keypair, pubkey })  
    }  
      
    /// Obtener public key  
    pub fn pubkey(&self) -> solana_sdk::pubkey::Pubkey {  
        self.pubkey  
    }  
      
    /// Firmar mensaje  
    pub fn sign_message(&self, message: &[u8]) -> solana_sdk::signature::Signature {  
        self.keypair.sign_message(message)  
    }  
      
    /// Obtener referencia al keypair para transacciones  
    pub fn keypair(&self) -> &Keypair {  
        &self.keypair  
    }  
}  
```  
  
**Tests obligatorios:**  
  
- `test_load_valid_keypair()` - Carga correcta  
- `test_invalid_key_fails()` - Rechaza keys inválidas  
- `test_signing()` - Firma mensajes correctamente  
  
-----  
  
### Módulo 2: solana/client.rs  
  
**Propósito:** Cliente RPC para Solana usando Helius  
  
**Responsabilidades:**  
  
- Conectar a Helius RPC  
- Enviar transacciones  
- Consultar balances  
- Obtener recent blockhash  
- Confirmar transacciones  
  
**Estructura principal:**  
  
```rust  
use solana_client::rpc_client::RpcClient;  
use solana_sdk::{  
    commitment_config::CommitmentConfig,  
    transaction::Transaction,  
    pubkey::Pubkey,  
};  
use anyhow::Result;  
  
pub struct SolanaClient {  
    rpc_client: RpcClient,  
    helius_api_key: String,  
}  
  
impl SolanaClient {  
    /// Crear cliente con Helius RPC  
    pub fn new_helius() -> Result<Self> {  
        let api_key = std::env::var("HELIUS_API_KEY")?;  
        let rpc_url = format!(  
            "https://mainnet.helius-rpc.com/?api-key={}",  
            api_key  
        );  
          
        let rpc_client = RpcClient::new_with_commitment(  
            rpc_url,  
            CommitmentConfig::confirmed(),  
        );  
          
        tracing::info!("✅ Cliente Solana (Helius) inicializado");  
          
        Ok(Self {  
            rpc_client,  
            helius_api_key: api_key,  
        })  
    }  
      
    /// Obtener balance de SOL  
    pub fn get_balance(&self, pubkey: &Pubkey) -> Result<u64> {  
        let lamports = self.rpc_client.get_balance(pubkey)?;  
        Ok(lamports)  
    }  
      
    /// Enviar transacción con propina  
    pub fn send_transaction_with_tip(  
        &self,  
        transaction: &Transaction,  
        tip_lamports: u64,  
    ) -> Result<solana_sdk::signature::Signature> {  
        // Implementación de envío con propina  
        let signature = self.rpc_client.send_and_confirm_transaction(transaction)?;  
          
        tracing::info!(  
            "✅ TX enviada: {} (propina: {} lamports)",  
            signature,  
            tip_lamports  
        );  
          
        Ok(signature)  
    }  
      
    /// Obtener recent blockhash  
    pub fn get_latest_blockhash(&self) -> Result<solana_sdk::hash::Hash> {  
        Ok(self.rpc_client.get_latest_blockhash()?)  
    }  
}  
```  
  
-----  
  
### Módulo 3: pumpfun/buy.rs  
  
**Propósito:** Comprar tokens en pump.fun  
  
**Responsabilidades:**  
  
- Construir instrucción de compra  
- Calcular slippage  
- Añadir propina  
- Ejecutar compra  
- Confirmar transacción  
  
**Estructura principal:**  
  
```rust  
use solana_sdk::{  
    transaction::Transaction,  
    instruction::Instruction,  
    pubkey::Pubkey,  
};  
use anyhow::Result;  
  
pub struct PumpFunBuyer {  
    program_id: Pubkey,  
}  
  
impl PumpFunBuyer {  
    pub fn new() -> Self {  
        let program_id = std::env::var("PUMPFUN_PROGRAM_ID")  
            .expect("PUMPFUN_PROGRAM_ID requerido")  
            .parse()  
            .expect("PUMPFUN_PROGRAM_ID inválido");  
          
        Self { program_id }  
    }  
      
    /// Comprar tokens en pump.fun  
    ///   
    /// # Parámetros  
    /// - `token_mint`: Dirección del token a comprar  
    /// - `sol_amount`: Cantidad de SOL a gastar (en lamports)  
    /// - `slippage_percent`: Slippage máximo permitido  
    /// - `priority_fee`: Propina para prioridad (lamports)  
    pub async fn buy_token(  
        &self,  
        token_mint: &Pubkey,  
        sol_amount: u64,  
        slippage_percent: f64,  
        priority_fee: u64,  
    ) -> Result<solana_sdk::signature::Signature> {  
        // Validaciones  
        let max_sol = std::env::var("MAX_SOL_PER_TRADE")?  
            .parse::<f64>()?;  
        let sol_in_sol = sol_amount as f64 / 1_000_000_000.0;  
          
        if sol_in_sol > max_sol {  
            anyhow::bail!(  
                "Cantidad excede máximo: {} SOL > {} SOL",  
                sol_in_sol,  
                max_sol  
            );  
        }  
          
        tracing::info!(  
            "🛒 Comprando token {} con {} SOL (slippage: {}%, propina: {} lamports)",  
            token_mint,  
            sol_in_sol,  
            slippage_percent,  
            priority_fee  
        );  
          
        // Construir instrucción de compra  
        // NOTA: Esto depende del programa exacto de pump.fun  
        // Necesitas reverse engineer o documentación oficial  
          
        let buy_instruction = self.build_buy_instruction(  
            token_mint,  
            sol_amount,  
            slippage_percent,  
        )?;  
          
        // TODO: Añadir propina como instrucción  
        // TODO: Construir y firmar transacción  
        // TODO: Enviar transacción  
        // TODO: Confirmar transacción  
          
        unimplemented!("Implementar según programa de pump.fun")  
    }  
      
    fn build_buy_instruction(  
        &self,  
        token_mint: &Pubkey,  
        sol_amount: u64,  
        slippage: f64,  
    ) -> Result<Instruction> {  
        // Implementar según programa pump.fun  
        unimplemented!()  
    }  
}  
```  
  
**⚠️ CRÍTICO:**  
  
- Necesitas la estructura exacta del programa pump.fun  
- Verificar accounts requeridos  
- Validar slippage correctamente  
- Confirmar transacción antes de reportar éxito  
  
-----  
  
### Módulo 4: helius/priority_fees.rs  
  
**Propósito:** Calcular y añadir propinas para priorizar transacciones  
  
**Responsabilidades:**  
  
- Obtener recommended priority fee de Helius  
- Construir instrucción de compute budget  
- Añadir propina a transacciones  
  
**Estructura principal:**  
  
```rust  
use solana_sdk::{  
    instruction::Instruction,  
    pubkey::Pubkey,  
    compute_budget::ComputeBudgetInstruction,  
};  
use reqwest;  
use serde::{Deserialize, Serialize};  
use anyhow::Result;  
  
#[derive(Debug, Deserialize)]  
pub struct PriorityFeeEstimate {  
    pub priority_fee_estimate: u64,  
}  
  
pub struct PriorityFeeManager {  
    helius_api_key: String,  
    client: reqwest::Client,  
}  
  
impl PriorityFeeManager {  
    pub fn new() -> Self {  
        let helius_api_key = std::env::var("HELIUS_API_KEY")  
            .expect("HELIUS_API_KEY requerida");  
          
        Self {  
            helius_api_key,  
            client: reqwest::Client::new(),  
        }  
    }  
      
    /// Obtener recommended priority fee de Helius  
    pub async fn get_recommended_fee(&self) -> Result<u64> {  
        let url = format!(  
            "https://mainnet.helius-rpc.com/?api-key={}",  
            self.helius_api_key  
        );  
          
        let response: PriorityFeeEstimate = self.client  
            .post(&url)  
            .json(&serde_json::json!({  
                "jsonrpc": "2.0",  
                "id": "1",  
                "method": "getPriorityFeeEstimate",  
                "params": [{  
                    "accountKeys": ["11111111111111111111111111111111"],  
                    "options": {  
                        "recommendedPriorityLevel": "High"  
                    }  
                }]  
            }))  
            .send()  
            .await?  
            .json()  
            .await?;  
          
        Ok(response.priority_fee_estimate)  
    }  
      
    /// Crear instrucciones de compute budget con propina  
    pub fn create_priority_fee_instructions(  
        &self,  
        priority_fee: u64,  
    ) -> Vec<Instruction> {  
        vec![  
            // Set compute unit price (propina)  
            ComputeBudgetInstruction::set_compute_unit_price(priority_fee),  
            // Set compute unit limit  
            ComputeBudgetInstruction::set_compute_unit_limit(300_000),  
        ]  
    }  
      
    /// Calcular propina según urgencia  
    pub async fn calculate_tip(&self, urgency: TipUrgency) -> Result<u64> {  
        let recommended = self.get_recommended_fee().await?;  
          
        let multiplier = match urgency {  
            TipUrgency::Low => 0.5,  
            TipUrgency::Medium => 1.0,  
            TipUrgency::High => 2.0,  
            TipUrgency::Ultra => 5.0,  
        };  
          
        let tip = (recommended as f64 * multiplier) as u64;  
          
        // Validar límites  
        let min_tip = std::env::var("MIN_PRIORITY_FEE")?.parse()?;  
        let max_tip = std::env::var("MAX_PRIORITY_FEE")?.parse()?;  
          
        let final_tip = tip.clamp(min_tip, max_tip);  
          
        tracing::info!(  
            "💰 Propina calculada: {} lamports ({:?})",  
            final_tip,  
            urgency  
        );  
          
        Ok(final_tip)  
    }  
}  
  
#[derive(Debug, Clone, Copy)]  
pub enum TipUrgency {  
    Low,      // 0.5x recommended  
    Medium,   // 1.0x recommended  
    High,     // 2.0x recommended  
    Ultra,    // 5.0x recommended  
}  
```  
  
-----  
  
### Módulo 5: dexscreener/monitor.rs  
  
**Propósito:** Monitorear tokens nuevos y tendencias en Dexscreener  
  
**Responsabilidades:**  
  
- Buscar tokens de Solana  
- Filtrar por volumen/liquidez  
- Detectar tokens nuevos  
- Analizar tendencias  
  
**Estructura principal:**  
  
```rust  
use reqwest;  
use serde::{Deserialize, Serialize};  
use anyhow::Result;  
  
#[derive(Debug, Deserialize)]  
pub struct DexscreenerPair {  
    pub chainId: String,  
    pub dexId: String,  
    pub url: String,  
    pub pairAddress: String,  
    pub baseToken: TokenInfo,  
    pub quoteToken: TokenInfo,  
    pub priceNative: String,  
    pub priceUsd: Option<String>,  
    pub volume: VolumeInfo,  
    pub priceChange: PriceChangeInfo,  
    pub liquidity: Option<LiquidityInfo>,  
}  
  
#[derive(Debug, Deserialize)]  
pub struct TokenInfo {  
    pub address: String,  
    pub name: String,  
    pub symbol: String,  
}  
  
#[derive(Debug, Deserialize)]  
pub struct VolumeInfo {  
    pub h24: f64,  
    pub h6: f64,  
    pub h1: f64,  
    pub m5: f64,  
}  
  
#[derive(Debug, Deserialize)]  
pub struct PriceChangeInfo {  
    pub h24: f64,  
    pub h6: f64,  
    pub h1: f64,  
    pub m5: f64,  
}  
  
#[derive(Debug, Deserialize)]  
pub struct LiquidityInfo {  
    pub usd: Option<f64>,  
    pub base: f64,  
    pub quote: f64,  
}  
  
pub struct DexscreenerMonitor {  
    api_url: String,  
    client: reqwest::Client,  
}  
  
impl DexscreenerMonitor {  
    pub fn new() -> Self {  
        let api_url = std::env::var("DEXSCREENER_API_URL")  
            .unwrap_or_else(|_| "https://api.dexscreener.com/latest".to_string());  
          
        Self {  
            api_url,  
            client: reqwest::Client::new(),  
        }  
    }  
      
    /// Buscar token por dirección  
    pub async fn search_token(&self, token_address: &str) -> Result<Vec<DexscreenerPair>> {  
        let url = format!("{}/dex/tokens/{}", self.api_url, token_address);  
          
        #[derive(Deserialize)]  
        struct Response {  
            pairs: Option<Vec<DexscreenerPair>>,  
        }  
          
        let response: Response = self.client  
            .get(&url)  
            .send()  
            .await?  
            .json()  
            .await?;  
          
        Ok(response.pairs.unwrap_or_default())  
    }  
      
    /// Obtener trending tokens en Solana  
    pub async fn get_trending_solana(&self) -> Result<Vec<DexscreenerPair>> {  
        // Implementar según API de Dexscreener  
        // Puede requerir endpoint específico o filtrado manual  
        unimplemented!()  
    }  
      
    /// Filtrar tokens por criterios  
    pub fn filter_by_criteria(  
        &self,  
        pairs: Vec<DexscreenerPair>,  
        min_liquidity_usd: f64,  
        min_volume_24h: f64,  
    ) -> Vec<DexscreenerPair> {  
        pairs.into_iter()  
            .filter(|pair| {  
                // Filtrar por liquidez  
                let has_liquidity = pair.liquidity  
                    .as_ref()  
                    .and_then(|l| l.usd)  
                    .map(|usd| usd >= min_liquidity_usd)  
                    .unwrap_or(false);  
                  
                // Filtrar por volumen  
                let has_volume = pair.volume.h24 >= min_volume_24h;  
                  
                has_liquidity && has_volume  
            })  
            .collect()  
    }  
}  
```  
  
-----  
  
### Módulo 6: gmgn/analytics.rs  
  
**Propósito:** Obtener análisis y datos de tokens desde GMGN  
  
**Estructura principal:**  
  
```rust  
use reqwest;  
use serde::{Deserialize, Serialize};  
use anyhow::Result;  
  
#[derive(Debug, Deserialize)]  
pub struct GMGNTokenData {  
    pub address: String,  
    pub symbol: String,  
    pub name: String,  
    pub holders: Option<u64>,  
    pub market_cap: Option<f64>,  
    // Más campos según API  
}  
  
pub struct GMGNClient {  
    api_url: String,  
    client: reqwest::Client,  
}  
  
impl GMGNClient {  
    pub fn new() -> Self {  
        let api_url = std::env::var("GMGN_API_URL")  
            .unwrap_or_else(|_| "https://gmgn.ai/api".to_string());  
          
        Self {  
            api_url,  
            client: reqwest::Client::new(),  
        }  
    }  
      
    /// Obtener datos de token  
    pub async fn get_token_data(&self, token_address: &str) -> Result<GMGNTokenData> {  
        // Implementar según API de GMGN  
        unimplemented!()  
    }  
}  
```  
  
-----  
  
### Módulo 7: telegram/commands.rs  
  
**Propósito:** Comandos del bot de Telegram  
  
**Comandos principales:**  
  
```rust  
use teloxide::utils::command::BotCommands;  
  
#[derive(BotCommands, Clone)]  
#[command(rename_rule = "lowercase", description = "Comandos:")]  
pub enum Command {  
    #[command(description = "Iniciar bot")]  
    Start,  
      
    #[command(description = "Ver balance")]  
    Balance,  
      
    #[command(description = "Comprar token: /buy <address> <sol_amount>")]  
    Buy(String, String),  
      
    #[command(description = "Vender token: /sell <address> <percentage>")]  
    Sell(String, String),  
      
    #[command(description = "Ver posiciones abiertas")]  
    Positions,  
      
    #[command(description = "Buscar token: /search <address>")]  
    Search(String),  
      
    #[command(description = "Top trending")]  
    Trending,  
      
    #[command(description = "Configuración")]  
    Config,  
      
    #[command(description = "Ayuda")]  
    Help,  
}  
```  
  
-----  
  
### Módulo 8: trading/risk.rs  
  
**Propósito:** Gestión de riesgo  
  
**Validaciones obligatorias:**  
  
```rust  
pub struct RiskManager {  
    max_sol_per_trade: f64,  
    max_slippage: f64,  
    auto_stop_loss: f64,  
    auto_take_profit: f64,  
}  
  
impl RiskManager {  
    pub fn from_env() -> Result<Self> {  
        Ok(Self {  
            max_sol_per_trade: std::env::var("MAX_SOL_PER_TRADE")?.parse()?,  
            max_slippage: std::env::var("MAX_SLIPPAGE_PERCENT")?.parse()?,  
            auto_stop_loss: std::env::var("AUTO_STOP_LOSS_PERCENT")?.parse()?,  
            auto_take_profit: std::env::var("AUTO_TAKE_PROFIT_PERCENT")?.parse()?,  
        })  
    }  
      
    /// Validar operación de compra  
    pub fn validate_buy(&self, sol_amount: f64, slippage: f64) -> Result<()> {  
        if sol_amount > self.max_sol_per_trade {  
            anyhow::bail!("Cantidad excede máximo: {}", self.max_sol_per_trade);  
        }  
          
        if slippage > self.max_slippage {  
            anyhow::bail!("Slippage excede máximo: {}%", self.max_slippage);  
        }  
          
        Ok(())  
    }  
      
    /// Calcular stop loss  
    pub fn calculate_stop_loss(&self, entry_price: f64) -> f64 {  
        entry_price * (1.0 - self.auto_stop_loss / 100.0)  
    }  
      
    /// Calcular take profit  
    pub fn calculate_take_profit(&self, entry_price: f64) -> f64 {  
        entry_price * (1.0 + self.auto_take_profit / 100.0)  
    }  
}  
```  
  
-----  
  
## 🚀 DEPLOYMENT Y SCRIPTS {#deployment-scripts}  
  
### Script: install.sh  
  
```bash  
#!/bin/bash  
set -e  
  
echo "🚀 Instalando Solana Memecoin Bot..."  
  
# Verificar Solana CLI instalado  
if ! command -v solana &> /dev/null; then  
    echo "⚠️  Solana CLI no encontrado. Instalando..."  
    sh -c "$(curl -sSfL https://release.solana.com/stable/install)"  
fi  
  
# Verificar Rust  
if ! command -v cargo &> /dev/null; then  
    echo "❌ Rust no instalado. Instala desde: https://rustup.rs"  
    exit 1  
fi  
  
# Compilar  
echo "📦 Compilando proyecto..."  
cargo build --release  
  
# Configurar .env  
if [ ! -f ".env" ]; then  
    echo "📋 Creando .env..."  
    cp .env.example .env  
    echo ""  
    echo "⚠️  IMPORTANTE: Configura .env con tus credenciales"  
    echo "   Especialmente:"  
    echo "   - SOLANA_PRIVATE_KEY (usar wallet separada para bot)"  
    echo "   - HELIUS_API_KEY"  
    echo "   - TELOXIDE_TOKEN"  
    echo "   - AUTHORIZED_CHAT_ID"  
    read -p "Presiona Enter cuando hayas configurado .env..."  
fi  
  
echo "✅ Instalación completada"  
echo ""  
echo "⚠️  RECORDATORIOS DE SEGURIDAD:"  
echo "   1. Usa una wallet separada SOLO para el bot"  
echo "   2. No guardes grandes cantidades de SOL en ella"  
echo "   3. Haz backup de la private key"  
echo "   4. NUNCA compartas el .env"  
echo ""  
echo "Ejecutar bot: cargo run --release"  
```  
  
### Script: backup_wallet.sh  
  
```bash  
#!/bin/bash  
  
echo "💾 Backup de Wallet"  
echo "===================="  
echo ""  
echo "⚠️  Tu private key está en el archivo .env"  
echo "⚠️  NUNCA la compartas con nadie"  
echo ""  
echo "Public Key:"  
grep SOLANA_PUBLIC_KEY .env  
echo ""  
echo "Para hacer backup:"  
echo "1. Copia el contenido de .env a un lugar seguro"  
echo "2. Considera usar un password manager"  
echo "3. NO lo subas a GitHub"  
```  
  
### Script: check_balance.sh  
  
```bash  
#!/bin/bash  
  
source .env  
  
echo "💰 Balance de Wallet"  
echo "===================="  
echo ""  
echo "Wallet: $SOLANA_PUBLIC_KEY"  
echo ""  
  
solana balance $SOLANA_PUBLIC_KEY --url mainnet-beta  
  
echo ""  
echo "Para añadir SOL:"  
echo "solana transfer $SOLANA_PUBLIC_KEY <amount> --from <your-wallet>"  
```  
  
-----  
  
## ✅ TESTING Y SEGURIDAD {#testing-seguridad}  
  
### Tests Críticos Obligatorios  
  
```rust  
#[cfg(test)]  
mod tests {  
    use super::*;  
  
    #[test]  
    fn test_validate_max_trade_amount() {  
        // Verificar límites de trading  
    }  
  
    #[test]  
    fn test_slippage_validation() {  
        // Verificar slippage  
    }  
  
    #[test]  
    fn test_private_key_never_logged() {  
        // Asegurar que private key nunca aparece en logs  
    }  
  
    #[tokio::test]  
    async fn test_transaction_confirmation() {  
        // Verificar que TX se confirman antes de reportar éxito  
    }  
}  
```  
  
### Checklist de Seguridad  
  
**ANTES de usar en mainnet:**  
  
- [ ] Private key en .env, NUNCA en código  
- [ ] .env en .gitignore  
- [ ] Wallet separada solo para bot  
- [ ] Límites de MAX_SOL_PER_TRADE configurados  
- [ ] Validación de authorized_chat_id  
- [ ] Confirmación de usuario para trades  
- [ ] Logging de todas las operaciones  
- [ ] Tests de slippage  
- [ ] Tests de límites  
- [ ] Backup de private key  
- [ ] Stop loss configurado  
- [ ] Take profit configurado  
  
-----  
  
## ✅ CHECKLIST FINAL {#checklist-final}  
  
### Antes de Entregar  
  
**Fase 1: Configuración ✅**  
  
- [ ] Cargo.toml con dependencias Solana verificadas  
- [ ] .env.example completo con TODAS las variables  
- [ ] .gitignore incluye .env  
- [ ] README.md con warnings de seguridad  
  
**Fase 2: Wallet y Solana ✅**  
  
- [ ] wallet/keypair.rs: carga segura de keys  
- [ ] solana/client.rs: cliente Helius RPC  
- [ ] solana/transaction.rs: construcción de TX  
  
**Fase 3: Trading ✅**  
  
- [ ] pumpfun/buy.rs: compra de tokens  
- [ ] pumpfun/sell.rs: venta de tokens  
- [ ] trading/risk.rs: validaciones de riesgo  
  
**Fase 4: Propinas ✅**  
  
- [ ] helius/priority_fees.rs: cálculo de propinas  
- [ ] Instrucciones de compute budget  
  
**Fase 5: Integración APIs ✅**  
  
- [ ] dexscreener/monitor.rs: seguimiento tokens  
- [ ] gmgn/analytics.rs: análisis de mercado  
  
**Fase 6: Telegram ✅**  
  
- [ ] telegram/commands.rs: comandos del bot  
- [ ] telegram/alerts.rs: notificaciones  
- [ ] Autorización por chat_id  
  
**Fase 7: Seguridad ✅**  
  
- [ ] Validaciones de límites  
- [ ] Confirmación de usuario  
- [ ] Logging completo  
- [ ] Tests de seguridad  
  
**Fase 8: Documentación ✅**  
  
- [ ] README.md con guía completa  
- [ ] SECURITY.md con mejores prácticas  
- [ ] Comentarios en código  
- [ ] TODO en español  
  
-----  
  
## 🎯 INSTRUCCIONES FINALES PARA GEMINI  
  
### Al Recibir Este Manual:  
  
1. ✅ **LEE COMPLETO** - Especialmente partes de seguridad  
1. ✅ **VERIFICA** APIs de Pump.fun, Helius, Dexscreener  
1. ✅ **CONSULTA** versiones de solana-sdk en crates.io  
1. ✅ **SIGUE** formato de salida con comandos gedit  
1. ✅ **GENERA** código SEGURO para mainnet  
1. ✅ **VALIDA** límites y riesgos  
1. ✅ **DOCUMENTA** en español  
1. ✅ **ADVIERTE** sobre seguridad  
  
### Prioridades:  
  
1. **SEGURIDAD** - Manejo de fondos reales  
1. **FUNCIONALIDAD** - Trading que funcione  
1. **VALIDACIÓN** - Límites y confirmaciones  
1. **DOCUMENTACIÓN** - Advertencias claras  
  
-----  
  
## ⚠️ ADVERTENCIAS CRÍTICAS  
  
```  
⚠️⚠️⚠️ ESTE BOT MANEJA DINERO REAL ⚠️⚠️⚠️  
  
1. USA WALLET SEPARADA solo para el bot  
2. NO guardes grandes cantidades de SOL  
3. PRUEBA primero en DEVNET  
4. VERIFICA cada transacción  
5. CONFIGURA límites bajos al inicio  
6. HAZ backup de private key  
7. NUNCA compartas .env  
8. MONITOREA el bot constantemente  
  
⚠️ Los errores pueden resultar en PÉRDIDA TOTAL DE FONDOS  
⚠️ El trading de memcoins es EXTREMADAMENTE ARRIESGADO  
⚠️ Solo usa fondos que puedas permitirte PERDER  
```  
  
-----  
  
**🎉 FIN DEL MANUAL 🎉**  
  
**Versión:** 1.0    
**Blockchain:** Solana Mainnet    
**Fecha:** Febrero 2026    
**Estado:** Production Ready (con precaución) ⚠️  
