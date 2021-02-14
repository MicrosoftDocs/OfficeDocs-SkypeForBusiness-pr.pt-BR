---
title: Calculadora de Planejamento de Capacidade do Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/1/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: 'Resumo: como usar a ferramenta Calculadora de Capacidade.'
ms.openlocfilehash: ca7266f5a18e21dbb964f18a791de9b8903a7f0c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802991"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a>Calculadora de Planejamento de Capacidade do Skype for Business Server
 
**Resumo:** Como usar a Ferramenta Calculadora de Capacidade.

> [!NOTE]
> Este artigo faz referência aos downloads do Skype for Business Server 2015, mas se aplica a:
> - Skype for Business Server 2019.
> - Skype for Business Server 2015.
  
A Calculadora de Capacidade do [Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=51196) e a Calculadora de Capacidade do Skype for Business Server [2019](https://www.microsoft.com/download/details.aspx?id=57509) ampliam a Ferramenta de Planejamento do [Skype for Business](https://www.microsoft.com/download/details.aspx?id=50357) e sua documentação de implantação ( Planeje sua implantação do Skype for Business Server[2015](../plan-your-deployment/plan-your-deployment.md) e planeje sua implantação do [Skype for Business Server 2019,](../../SfBServer2019/plan/plan-your-deployment-2019.md) respectivamente). Use a calculadora depois de revisar o guia e criar uma topologia recomendada usando a Ferramenta de Planejamento.
  
A Calculadora de capacidade do Skype for Business Server ajuda a determinar os requisitos do servidor com base no número de usuários e nas ferramentas de comunicação que sua organização usa. Depois de determinar seu perfil de usuário e as funções que deseja habilitar para seus usuários, use a calculadora para determinar o número de servidores, memória e largura de banda necessários. Esta versão da calculadora não fornece orientações para requisitos de E/S de disco.
  
Você pode se beneficiar mais com a calculadora se tiver informações precisas e detalhadas sobre seu perfil de usuário específico. Por exemplo, a porcentagem de usuários habilitados para voz, a média de chamadas por usuário por hora, a duração da chamada e a porcentagem de usuários simultâneos em conferências podem fazer uma diferença enorme nos requisitos do servidor. A precisão das recomendações criadas pela calculadora depende da precisão das informações fornecidas.
  
Depois de usar a Ferramenta de Planejamento e a Calculadora de Planejamento de Capacidade, você deve simular sua carga proposta e planejada para garantir que o Skype for Business Server seja provisionado adequadamente. Para realizar testes de estresse sob uma carga simulada, use a Ferramenta de Stress and Performance do [Skype for Business Server](https://www.microsoft.com/download/details.aspx?id=50367) documentada na Ferramenta de Stress and Performance do Skype for Business [Server.](https://technet.microsoft.com/library/mt631400.aspx)
  
## <a name="using-the-capacity-calculator"></a>Usando a Calculadora de Capacidade

A calculadora é uma planilha do Microsoft Excel. Suas células de entrada estão coloridas em laranja. Os valores padrão são inseridos nas células (para o Skype for Business Server 2015, 80.000 usuários em um pool com doze Servidores front-end, enquanto para o Skype for Business Server 2019, 106.000 usuários em um pool com dezesseis servidores front-end), mas você deve alterar esses valores para corresponder às necessidades da sua organização.
  
O modelo de uso contém as seções a seguir. Para calcular seus requisitos de capacidade, insira dados conforme descrito começando na parte superior da planilha e trabalhando linha por linha: 
  
 **Sistema de Mensagens Instantâneas e Presença**
  
- Em **Número de Usuários,** digite o número de usuários que serão assinados de uma só vez. Normalmente, esse número é 80% do número total de usuários provisionados. Na maioria das situações, 100% dos usuários simultâneos serão habilitados para IM e Presença. O padrão é 80.000 para o Skype for Business Server 2015 e 106.000 usuários para o Skype for Business Server 2019.
    
- **O número médio de contatos na lista de** contatos indica o número de contatos que estamos usando para validar seus requisitos de sistema. Esse número é fixo e não é algo que você deve alterar.
    
  **Enterprise Voice**
  
- Em **Usuários habilitados para o Enterprise Voice,** digite a porcentagem de seus usuários habilitados para o Enterprise Voice. O padrão é 60%. 
    
- Em Número médio de chamadas por usuário por hora **(pico),** digite o número de chamadas por hora que você espera que o usuário médio participe durante os horários de pico de carga. O padrão é 4. 
    
- Em **Porcentagem de chamadas que usam bypass de mídia,** digite a porcentagem de chamadas feitas por seus usuários que ignorarão o Servidor de Mediação. O padrão é 65%, mas pode ser menor se você estiver espalhado geograficamente ou tiver uma grande porcentagem de usuários que trabalham em casa.
    
- Em Porcentagem de usuários de voz envolvidos em chamadas **UC-PSTN,** digite a porcentagem de chamadas da sua organização que são chamadas telefônicas UC-PSTN. O padrão é 60%.
    
- Porcentagem de usuários de voz envolvidos em chamadas **UC-UC** mostra a porcentagem de usuários habilitados para o Enterprise Voice que serão habilitados somente para chamadas UC-UC. Esse número é calculado com base no que você instrui para Porcentagem de usuários de voz habilitados para chamadas **UC-PSTN.** 
    
  **Conferências**
  
- Em **Porcentagem de usuários em conferências simultâneas,** digite a porcentagem de usuários que participarão de conferências ao mesmo tempo. O padrão é 5%. 
    
- Em Porcentagem de conferências com IM de grupo apenas **(sem voz),** digite a porcentagem de conferências que envolverão apenas mensagens instantâneas e não incluem áudio. O padrão é 10%
    
- Em **Porcentagem de usuários que** usam conferência discado, digite a porcentagem de participantes em conferências que usarão a conferência discado de uma só vez. O padrão é 15%.
    
- Em **Porcentagem de conferências usando voz,** digite a porcentagem de conferências que incluirão áudio. 
    
  - Se 20% de suas conferências de voz também incluirem vídeo normal, marque a caixa de seleção Incluir vídeo **(sem Multi View).**
    
  - Se 20% de suas conferências também incluirem vídeo multi-exibição, marque a caixa de seleção **Incluir Multivisão.**
    
  - Se 50% de suas conferências de voz também incluirem o compartilhamento de aplicativos, marque a caixa de seleção Incluir **compartilhamento de** aplicativos.
    
  - Se 20% de suas conferências de voz incluirem carregamentos de dados, como apresentações do PowerPoint, marque a caixa de seleção Incluir **webconferência.**
    
  **Mobilidade**
  
- Em **Porcentagem de usuários habilitados** para Mobilidade, digite a porcentagem de seus usuários que serão habilitados para se conectar ao Skype for Business Server usando dispositivos móveis. O padrão é 40%. 
    
Quando você tiver inserido todas as informações necessárias, a calculadora de capacidade estima seus requisitos. As células amarelas mostram valores calculados para requisitos de CPU, memória e largura de banda com base em testes realizados nos laboratórios de desempenho do Skype for Business Server. Os números são fornecidos como uma diretriz, e nem todas as variações são testadas e validadas. Os seguintes valores são calculados: 
  
- **CPU de front-end:** porcentagem de uso da CPU se toda a carga estava sendo manipulada por um Servidor front-end com as mesmas especificações que o servidor usado no teste (consulte a descrição no final deste artigo).
    
- **Rede em Mbps: requisitos** de largura de banda em megabits por segundo (Mbps) para a carga de trabalho correspondente.
    
- **Memória em GB:** memória necessária em gigabytes (GB) para a carga de trabalho correspondente.
    
As células verdes mostram recomendações para o modelo de uso inserido. 
  
- Total de servidores **front-end:** o número de servidores físicos necessários se baseia em servidores dedicados que executam o Skype for Business Server 2015 com processador duplo, hex-core, com 2.260 megaciclos ou o Skype for Business Server 2019 com Intel Xeon E5-2673 v3, processador duplo, hex-core.
    
    Observe que a habilitação do hyperthreading é recomendada e comprovadamente melhorou o desempenho para servidores que suportam áudio/vídeo.
    
- **Servidores de** Borda : o número de Servidores de Borda necessários, com base em 30% de todos os usuários simultâneos se comunicando por meio dos Servidores de Borda. Essa porcentagem não pode ser alterada na calculadora. 
    
- **Arquivamento/Registro** de Detalhes de Chamada/Armazenamento de Serviços de Qualidade da Experiência: o número de armazenamentos necessários para recursos de Arquivamento ou Monitoramento, se eles estão habilitados em sua organização.
    
- Servidor de Banco de Dados back-end necessário **(Pools obrigatórios)**: o número de servidores de banco de dados back-end necessários para dar suporte à carga de trabalho selecionada.
    
Além disso, na linha ao lado do Total de Servidores Front End, mais informações são fornecidas sobre a carga em seus servidores e rede para todas as cargas de trabalho planejadas combinadas.
  
- **Carga média da CPU**: o uso médio da CPU por servidor front-end.
    
- **Rede em Mbps**: a alocação de largura de banda necessária para dar suporte ao modelo de uso inserido.
    
- **Memória em GB:** Memória, em gigabytes, necessária para cada servidor front-end.
    
### <a name="adjusting-for-your-processors"></a>Ajustando para seus processadores

Todos os números de uso da CPU na planilha pressuem que cada servidor do Skype for Business Server 2015 tenha um processador duplo, núcleo hexagonal com 2,26 GHz, pelo menos 32 GB de memória e 8 ou mais unidades de disco rígido de 10.000 RPM com pelo menos 72 GB de espaço livre em disco. Para cada servidor Skype for Business Server 2019, todas as figuras de uso de CPU na planilha pressuem que cada servidor tenha um processador duplo, núcleo hex com Intel Xeon E5-2673 v3, pelo menos 64 GB de memória e 8 ou mais unidades de disco rígido de 10.000 RPM com pelo menos 72 GB de espaço livre em disco.
  
Se os servidores têm processadores diferentes, você pode ajustar os números para corresponder ao hardware.
  
