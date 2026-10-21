<div align="center">

<a href="README.md"><img src="https://api.iconify.design/flag/br-4x3.svg?width=24" alt="Português" title="Português" /></a>

<br><br>

<a href="https://github.com/OTheMandaloriano/ResetExplode">
  <img src="Assets/logo-badge.png" alt="RESET EXPLODE Logo" width="128" height="128" />
</a>

# RESET EXPLODE

**Central de diagnóstico, telemetria de hardware em tempo real, benchmarks gráficos e ferramentas de manutenção para Windows.**

<br>

[![.NET 8](https://img.shields.io/badge/.NET_8-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)](https://dotnet.microsoft.com/)
[![C#](https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=csharp&logoColor=white)](https://learn.microsoft.com/dotnet/csharp/)
[![WPF](https://img.shields.io/badge/WPF-0078D7?style=for-the-badge&logo=windows&logoColor=white)](https://learn.microsoft.com/dotnet/desktop/wpf/)
[![DirectX](https://img.shields.io/badge/DirectX_11_%2F_12-000000?style=for-the-badge&logo=directx&logoColor=white)](https://microsoft.github.io/DirectX-Specs/)
[![Windows](https://img.shields.io/badge/Windows-10_%7C_11-0078D4?style=for-the-badge&logo=windows11&logoColor=white)](https://microsoft.com/windows)

<br>

[![Versão](https://img.shields.io/badge/versão-v0.16-10B981?style=flat-square)](https://github.com/OTheMandaloriano/ResetExplode/releases/tag/latest)
[![Status do Build](https://img.shields.io/badge/build-estável-10B981?style=flat-square)](https://github.com/OTheMandaloriano/ResetExplode/releases)
[![Licença](https://img.shields.io/badge/licença-MIT-0EA5E9?style=flat-square)](LICENSE)
[![Arquitetura](https://img.shields.io/badge/arquitetura-x64-64748B?style=flat-square)](https://github.com/OTheMandaloriano/ResetExplode)

<br>

[Download Executável](https://github.com/OTheMandaloriano/ResetExplode/releases/tag/latest) • [Módulos e Recursos](#-módulos-e-recursos) • [Requisitos](#-requisitos-do-sistema) • [Como Rodar](#-como-rodar-do-código-fonte) • [Limitações](#-limitações-conhecidas)

</div>

---

## <img src="https://api.iconify.design/solar/info-circle-bold.svg?color=%230EA5E9&width=22" align="top" /> &nbsp;Visão Geral

O **RESET EXPLODE** é um aplicativo de desktop para Windows desenvolvido em C# e .NET 8 que reúne, em uma interface unificada e minimalista, as atribuições de múltiplos utilitários técnicos de monitoramento e teste de carga (como GPU-Z, Cinebench, FurMark, RTSS/Afterburner e CrystalDiskInfo).

Projetado para entusiastas de hardware, técnicos e jogadores, o software combina leitura de sensores em tempo real, bateria de testes com renderizadores 3D próprios (Direct3D 11 e Direct3D 12 Ray Tracing), detecção de gargalos, overlay de performance sem injeção de DLLs e ferramentas de configuração pós-formatação.

> [!IMPORTANT]
> O programa efetua leituras de registradores e sensores em baixo nível, além de gerenciar serviços e dispositivos. A execução com **privilégios de Administrador** é obrigatória.

---

## <img src="https://api.iconify.design/solar/download-square-bold.svg?color=%2310B981&width=22" align="top" /> &nbsp;Download e Execução Rápida

As compilações oficiais pré-construídas estão disponíveis na seção de lançamentos do repositório:

1. Acesse a página de [Releases do Repositório](https://github.com/OTheMandaloriano/ResetExplode/releases/tag/latest).
2. Baixe o executável autônomo `ResetExplode.exe` ou o pacote comprimido `ResetExplode.zip`.
3. Certifique-se de que o driver de sensores [PawnIO](#-requisitos-do-sistema) esteja instalado no sistema operacional.
4. Execute o arquivo com botão direito: **Executar como Administrador**.

---

## <img src="https://api.iconify.design/solar/widget-bold.svg?color=%230EA5E9&width=22" align="top" /> &nbsp;Módulos e Recursos

O aplicativo organiza suas funcionalidades em seis categorias principais com carregamento paralelo e instantâneo:

### 1. Monitoramento e Telemetria
- **Visão Geral e Painel Dinâmico**: Gráficos de área de CPU versus GPU (temperatura, carga e consumo com intervalos de 1, 5 e 15 minutos), resumo de hardware, anéis de consumo de RAM, VRAM e discos.
- **Sensores em Tempo Real**: Telemetria ao vivo com taxa de atualização de 1 segundo (clocks, temperaturas, tensões, ventoinhas e potências), incluindo busca textual e filtros de visualização por circuito integrado.
- **Detecção Avançada de GPU (Estilo GPU-Z)**: Identificação completa de die, litografia, contagem de transistores, SMs, núcleos Tensor/RT, barramento PCIe negociado versus máximo, suporte a Resizable BAR, estados P-State, sensores NVML e códigos PerfCap.
- **Saúde e Diagnóstico S.M.A.R.T. de Discos**: Leitura direta via Windows Storage e drivers de integridade, apontando veredito (Bom, Atenção ou Ruim), temperatura de operação, horas de uso, ciclos de alimentação, desgaste percentual de SSD e alertas preditivos de falha.
- **Energia e Bateria**: Análise de notebooks com contagem de ciclos, capacidade de fábrica versus atual, veredito de desgaste, taxas de descarga em Watts e monitoramento de plano de energia do Windows.
- **Diagnóstico de Conexão e Rede**: Teste rápido de estabilidade em 30 segundos, medindo latência, jitter, perda de pacotes contra DNS públicos (1.1.1.1 e 8.8.8.8), bufferbloat sob carga e velocidade de download e upload.
- **Exportação de Relatórios Técnicos**: Geração de dossiê completo de inventário e saúde em formato HTML padronizado ou JSON estruturado.

### 2. Desempenho e Stress Tests
- **RESET BENCH (CPU Path Tracer)**: Renderizador monocromático próprio com iluminação global, materiais metálicos e refração em vidro. Modos Multi-core e Single-core baseados em sementes de cálculo determinísticas para aferição pontual de pontuação por amostras/segundo.
- **Cena de Jogo (GPU D3D11)**: Teste automatizado com renderização de terreno procedural, instanciamento de 40.000 árvores, mapas de sombra 4096² com filtragem PCF e pós-processamento HDR em 1080p, 1440p e 4K.
- **Ray Tracing GPU (DXR 1.1 Direct3D 12)**: Benchmark em compute shader puro que estressa diretamente os núcleos RT de placas RTX 20+, Radeon RX 6000+ e Intel Arc, calculando 4.000 objetos dinâmicos com reconstrução de aceleração TLAS frame a frame.
- **Stress Test de CPU e Memória**: Carga pesada contínua multithread (instruções inteiras e FPU) combinada com verificação de padrões em 40% a 80% da memória RAM livre, com desligamento automático programável por temperatura limite.
- **Stress de GPU (GpuBurn D3D11)**: Renderizador focado em consumo térmico máximo (análogo ao FurMark), com geometria complexa de torus e múltiplos passos de alpha blending, exibindo telemetria em tempo real de consumo em Watts e limitadores.

### 3. Jogos e Otimização
- **Detector de Gargalo**: Cruzamento analítico de equilíbrio entre processador e placa de vídeo em sessões de jogo, mapeando o percentual de tempo em que a taxa de quadros foi contida por CPU, GPU, limite térmico ou restrições de VRAM.
- **Overlay de Desempenho**: Janela transparente de monitoramento em tempo real (FPS, frametime, 1% low, consumo, temperaturas e frequências) posicionada sobre a janela do jogo ativo via atalho global `Ctrl+Shift+O`.
- **Biblioteca e Perfis por Título**: Inicializador integrado com detecção de instaladores (Steam, Epic Games, GOG e executáveis manuais), aplicando ajustes automáticos de prioridade de processo, plano de energia de alto desempenho e gravação de parâmetros de inicialização no `localconfig.vdf` da Steam.

### 4. Ferramentas de Manutenção
- **Gerenciador de Inicialização**: Inventário de entradas Run do registro do Windows (usuário e máquina, 32 e 64 bits) e pastas de inicialização, permitindo ligar, desligar ou remover itens com suporte à reversão em caso de engano.
- **Instalador de Aplicativos Pós-Formatação**: Automação de download e instalação silenciosa de utilitários essenciais (Steam, Google Chrome, Discord, Lightshot, 7-Zip, WinRAR e VLC) por meio do Microsoft Winget oficial.
- **Gerenciador de Drivers**: Auditoria de drivers instalados no sistema, verificação e download de versões oficiais NVIDIA com conferência de assinatura WHQL e atalhos diretos para suporte de fabricantes.

### 5. Suporte a Maker e Portas Seriais
- **Limpeza de Portas COM**: Varredura e desinstalação de identificadores fantasmas e números de portas seriais retidos no registro por dispositivos desconectados.
- **Diagnóstico e Reparo de Chips Seriais**: Diagnóstico automático de conversores USB-serial (CH340, CP2102, FTDI, Prolific e Arduino), com detecção de falhas de código 10, código 43 e reinstalação limpa.
- **Drivers Oficiais Embutidos**: Instaladores integrados e assinados para operação offline imediata, dispensando conexão com a internet.

### 6. Integração e Controle de Iluminação
- **Controle Unificado de RGB**: Ponte para gerenciamento de periféricos e gabinetes via Corsair iCUE (SDK v4), OpenRGB (servidor local para placas-mãe ASUS, MSI e Gigabyte) e Razer Chroma.
- **Modos Reativos**: Sincronização da cor e intensidade dos LEDs conforme a temperatura ou a porcentagem de uso do processador e da placa de vídeo.

---

## <img src="https://api.iconify.design/solar/checklist-minimalistic-bold.svg?color=%230EA5E9&width=22" align="top" /> &nbsp;Requisitos do Sistema

| Componente | Requisito Mínimo | Observações |
| :--- | :--- | :--- |
| **Sistema Operacional** | Windows 10 ou Windows 11 (64-bit) | Versões 1909 ou superior recomendadas |
| **Ambiente de Execução** | .NET 8 Desktop Runtime (x64) | Necessário apenas para build local (embutido no `.exe` da release) |
| **Driver de Sensores** | **PawnIO** | Essencial para a leitura de temperatura e consumo de CPU |
| **Placa de Vídeo** | Compatível com DirectX 11 | Suporte a DirectX 12 e DXR 1.1 obrigatório apenas para o benchmark de Ray Tracing |
| **Privilégios** | Acesso de Administrador | Obrigatório para acesso aos barramentos de hardware e chamadas WMI |

> [!NOTE]
> Para instalar o driver **PawnIO** de forma automática pelo terminal, execute:
> ```powershell
> winget install namazso.PawnIO
> ```
> O driver PawnIO substitui o driver legado WinRing0, eliminando bloqueios de segurança do Microsoft Defender.

---

## <img src="https://api.iconify.design/solar/code-square-bold.svg?color=%230EA5E9&width=22" align="top" /> &nbsp;Como Rodar do Código-Fonte

### Compilação e Depuração

Certifique-se de possuir o [.NET 8 SDK](https://dotnet.microsoft.com/download) instalado no ambiente:

```bash
# Clone o repositório
git clone https://github.com/OTheMandaloriano/ResetExplode.git

# Acesse o diretório
cd ResetExplode

# Restaure as dependências e inicie o aplicativo
dotnet run
```

### Gerando o Pacote de Distribuição

Para compilar um executável único e independente de runtime (autônomo para envio a outros computadores):

```cmd
publicar.bat
```

O script criará a pasta `..\ResetExplode-dist\` contendo o arquivo `ResetExplode.exe` compilado em modo Release, com todos os módulos essenciais unificados e sem dependências externas adicionais além do driver PawnIO.

---

## <img src="https://api.iconify.design/solar/layers-bold.svg?color=%230EA5E9&width=22" align="top" /> &nbsp;Arquitetura e Bibliotecas

O projeto faz uso de bibliotecas consagradas de baixo nível e padrões modernos do ecossistema .NET:

| Biblioteca / Recurso | Finalidade Técnica | Licenciamento |
| :--- | :--- | :--- |
| **LibreHardwareMonitorLib** | Comunicação com chips de monitoramento e sensores da placa-mãe | MPL 2.0 |
| **TraceEvent (Microsoft)** | Coleta de telemetria de taxas de quadros via ETW (sem injeção de DLLs) | MIT |
| **Vortice.Windows** | Bindings de baixo nível para Direct3D 11, Direct3D 12 e compilador DXC | MIT |
| **NVML (NVIDIA)** | Acesso a métricas corporativas e limitadores de clock e tensão em GPUs NVIDIA | Proprietária / SDK |
| **Windows WMI / PnP** | Extração de inventário do sistema operacional, memória e periféricos | Nativo Windows |

---

## <img src="https://api.iconify.design/solar/danger-triangle-bold.svg?color=%23F97316&width=22" align="top" /> &nbsp;Limitações Conhecidas

| Limitação | Causa Técnica | Comportamento Observado |
| :--- | :--- | :--- |
| **Sensores de placas-mãe específicas** | Variação de circuitos Super I/O no mercado | Caso o chip não seja homologado na biblioteca de monitoramento, certas rotações de ventoinha podem não ser exibidas. |
| **Overlay em tela cheia exclusiva** | O overlay opera como janela transparente com prioridade top-most via Direct3D | Jogos em modo exclusivo assumem controle total da superfície de renderização. O overlay requer modo janela ou janela sem bordas (borderless). |
| **Estimativa de FPS sem chave de API** | A integração detalhada utiliza a API da HowManyFPS | Sem chave configurada, o cálculo de FPS é aproximado com base no banco de dados local heurístico (`GameCatalog.cs`). |

---

## <img src="https://api.iconify.design/solar/shield-check-bold.svg?color=%230EA5E9&width=22" align="top" /> &nbsp;Licença

Este projeto é distribuído sob os termos da licença **MIT**. Consulte o arquivo [LICENSE](LICENSE) para mais detalhes.
