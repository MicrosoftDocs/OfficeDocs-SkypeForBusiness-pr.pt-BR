---
title: Calculadora de Planejamento de Capacidade do Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
ms.date: 2/1/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: 'Resumo: como usar a Ferramenta calculadora de capacidade.'
ms.openlocfilehash: 37df48310e14b31b42bbcaa9d8f5ef89ef7341e0
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62409954"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a>Calculadora de Planejamento de Capacidade do Skype for Business Server
 
**Resumo:** Como usar a Ferramenta calculadora de capacidade.

> [!NOTE]
> Este artigo faz referência Skype for Business Server downloads 2015, mas se aplica a:
> - Skype for Business Server 2019.
> - Skype for Business Server 2015.
  
A [calculadora Skype for Business Server capacidade do Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=51196) e Skype for Business Server [2019](https://www.microsoft.com/download/details.aspx?id=57509) ampliam a Ferramenta de Planejamento [Skype for Business e sua](https://www.microsoft.com/download/details.aspx?id=50357) documentação de implantação ([Planejar sua Skype for Business Server 2015 e](../plan-your-deployment/plan-your-deployment.md) [Planejar sua implantação Skype for Business Server 2019](../../SfBServer2019/plan/plan-your-deployment-2019.md), respectivamente). Use a calculadora depois de revisar o guia e criar uma topologia recomendada usando a Ferramenta de Planejamento.
  
A Skype for Business Server de capacidade ajuda você a determinar os requisitos do servidor com base no número de usuários e nas ferramentas de comunicação que sua organização usa. Depois de determinar seu perfil de usuário e as funções que deseja habilitar para seus usuários, use a calculadora para determinar o número de servidores, memória e largura de banda que você precisará. Esta versão da calculadora não fornece orientações para requisitos de E/S de disco.
  
Você pode se beneficiar mais com a calculadora se tiver informações precisas e detalhadas sobre seu perfil de usuário específico. Por exemplo, a porcentagem de usuários habilitados para voz, a média de chamadas por usuário por hora, a duração da chamada e a porcentagem de usuários simultâneos em conferências podem fazer uma grande diferença nos requisitos do servidor. A precisão das recomendações criadas pela calculadora depende da precisão das informações fornecidas.
  
Depois de usar a Ferramenta de Planejamento e a Calculadora de Planejamento de Capacidade, você deve simular sua carga proposta e planejada para garantir que o Skype for Business Server seja provisionado adequadamente. Para executar o teste de estresse em uma carga simulada, use a ferramenta Skype for Business Server stress e [desempenho](https://www.microsoft.com/download/details.aspx?id=50367) documentada na Skype for Business Server [Ferramenta de Desempenho e Estresse](./stress-and-performance-tool/stress-and-performance-tool.md).
  
## <a name="using-the-capacity-calculator"></a>Usando a Calculadora de Capacidade

A calculadora é uma Microsoft Excel de dados. Suas células de entrada são coloridas em laranja. Os valores padrão são inseridos nas células (para o Skype for Business Server 2015, 80.000 usuários em um pool com doze Servidores Front-End, enquanto para o Skype for Business Server 2019, 106.000 usuários em um pool com dezesseis Servidores Front-End), mas você deve alterar esses valores para corresponder às necessidades da sua organização.
  
O modelo de uso contém as seções a seguir. Para calcular seus requisitos de capacidade, insira dados conforme descrito começando na parte superior da planilha e trabalhando linha por linha: 
  
 **Mensagens Instantâneas e Presença**
  
- Em **Número de Usuários**, digite o número de usuários que serão assinados de uma vez. Esse número geralmente é 80% do número total de usuários provisionados. Na maioria das situações, 100% dos usuários simultâneos serão habilitados para IM e Presença. O padrão é 80.000 para Skype for Business Server 2015 e 106.000 usuários para Skype for Business Server 2019.
    
- **O número médio de contatos na lista de** contatos indica o número de contatos que estamos usando para validar seus requisitos do sistema. Esse número é fixo e não algo que você deve alterar.
    
  **Enterprise Voice**
  
- Em **Usuários habilitados para Enterprise Voice**, digite a porcentagem de seus usuários habilitados para Enterprise Voice. O padrão é 60%. 
    
- Em **Número médio de** chamadas por usuário por hora (pico), digite o número de chamadas por hora que você espera que o usuário médio participe durante os horários de pico de carga. O padrão é 4. 
    
- Em **Porcentagem de chamadas que usam bypass de mídia**, digite a porcentagem de chamadas feitas por seus usuários que ignorarão o Servidor de Mediação. O padrão é 65%, mas pode ser menor se você estiver espalhado geograficamente ou tiver uma grande porcentagem de usuários que trabalham em casa.
    
- Em **Porcentagem de usuários de voz envolvidos em chamadas UC-PSTN**, digite a porcentagem de chamadas da sua organização que são chamadas telefônicas UC-PSTN. O padrão é 60%.
    
- **Porcentagem de usuários de voz envolvidos em chamadas UC-UC** mostra a porcentagem de usuários habilitados para Enterprise Voice que serão habilitados somente para chamadas UC-UC. Esse número é calculado com base no que você instrui para Porcentagem de usuários de **voz habilitados para chamadas UC-PSTN**. 
    
  **Conferências**
  
- Em **Porcentagem de usuários em conferências simultâneas**, digite a porcentagem de usuários que participarão de conferências ao mesmo tempo. O padrão é 5%. 
    
- Em **Porcentagem de conferências com IM de grupo somente (** sem voz), digite o percentual de conferências que envolverão apenas mensagens instantâneas e não incluir áudio. O padrão é 10%
    
- Em **Porcentagem de usuários que usam** conferência discagem, digite a porcentagem de participantes em conferências que estarão usando a conferência discagem de uma só vez. O padrão é 15%.
    
- Em **Porcentagem de conferências usando voz**, digite a porcentagem de conferências que incluirão áudio. 
    
  - Se 20% de suas conferências de voz também incluirem vídeo regular, marque a caixa de seleção Incluir **vídeo (sem Multi View** ).
    
  - Se 20% de suas conferências também incluirem vídeo Multi-View, marque a caixa **de seleção Incluir Multi-Exibição** .
    
  - Se 50% das conferências de voz também incluirem compartilhamento de aplicativos, marque a caixa de seleção **Incluir compartilhamento de** aplicativos.
    
  - Se 20% de suas conferências de voz incluirem carregamentos de dados, como PowerPoint apresentações, selecione a caixa de seleção Incluir **webconferência**.
    
  **Mobilidade**
  
- Em **Porcentagem de usuários habilitados para Mobilidade**, digite a porcentagem de seus usuários que serão habilitados para se conectar a Skype for Business Server usando dispositivos móveis. O padrão é 40%. 
    
Quando você tiver inserido todas as informações necessárias, a calculadora de capacidade estima seus requisitos. As células amarelas mostram valores calculados para os requisitos de CPU, memória e largura de banda com base em testes realizados Skype for Business Server laboratórios de desempenho. Os números são fornecidos como uma diretriz, nem todas as variações são testadas e validadas. Os seguintes valores são calculados: 
  
- **CPU front-end**: porcentagem de uso da CPU se toda a carga estivesse sendo manipulada por um Servidor Front-End com as mesmas especificações do servidor usado no teste (consulte a descrição no final deste artigo).
    
- **Rede em Mbps**: Requisitos de largura de banda em megabits por segundo (Mbps) para a carga de trabalho correspondente.
    
- **Memória em GB**: Memória necessária em gigabytes (GB) para a carga de trabalho correspondente.
    
As células verdes mostram recomendações para o modelo de uso inserido. 
  
- **Servidores front-end** totais: o número de servidores físicos necessários se baseia em servidores dedicados que executam o Skype for Business Server 2015 com processador duplo, hex-core, com 2.260 megaciclos ou Skype for Business Server 2019 com Intel Xeon E5-2673 v3, processador dual, hex-core.
    
    Observe que a habilitação do hiperthreading é recomendada e foi comprovada para melhorar o desempenho para servidores que suportam áudio/vídeo.
    
- **Servidores de Borda**: o número de Servidores de Borda necessários, com base em 30% de todos os usuários simultâneos que se comunicam por meio dos Servidores de Borda. Essa porcentagem não pode ser alterada na calculadora. 
    
- **Archiving/Call Detail Recording/Quality of Experience services Store**: o número de lojas necessárias para recursos de Arquivamento ou Monitoramento, se eles estão habilitados em sua organização.
    
- **Servidor de Banco de Dados de Back-End Obrigatório (Pools Obrigatórios)**: o número de servidores de banco de dados back-end necessários para dar suporte à carga de trabalho selecionada.
    
Além disso, na linha ao lado do Total de Servidores Front-End, mais informações são fornecidas sobre a carga em seus servidores e rede para todas as cargas de trabalho planejadas combinadas.
  
- **Carga média da CPU**: o uso médio da CPU por servidor Front-End.
    
- **Rede em Mbps**: a alocação de largura de banda necessária para dar suporte ao modelo de uso inserido.
    
- **Memória em GB**: Memória, em gigabytes, necessária para cada servidor Front-End.
    
### <a name="adjusting-for-your-processors"></a>Ajustando para seus processadores

Todos os números de uso da CPU na planilha pressuem que cada servidor Skype for Business Server 2015 tenha um processador duplo, hex-core com 2,26 GHz, pelo menos 32 GB de memória e 8 ou mais unidades de disco rígido de 10.000 RPM com pelo menos 72 GB de espaço livre em disco. Para cada servidor Skype for Business Server 2019, todos os números de uso da CPU na planilha pressuem que cada servidor tenha um processador duplo, hex-core com Intel Xeon E5-2673 v3, pelo menos 64 GB de memória e 8 ou mais unidades de disco rígido de 10.000 RPM com pelo menos 72 GB de espaço livre em disco.
  
Se seus servidores têm processadores diferentes, você pode ajustar os números para corresponder ao hardware.
