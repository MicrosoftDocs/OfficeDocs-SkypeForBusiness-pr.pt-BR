---
title: Calculadora de planejamento de capacidade do Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Resumo: como usar a ferramenta de calculadora de capacidade.'
ms.openlocfilehash: 1bb1c9cde82c1f2d6e487c3bc28520b630d59210
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031075"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a>Calculadora de planejamento de capacidade do Skype for Business Server
 
**Resumo:** Como usar a ferramenta de calculadora de capacidade.

> [!NOTE]
> Este artigo faz referência a downloads do Skype for Business Server 2015, mas se aplica a:
> - Skype for Business Server 2019.
> - Skype for Business Server 2015.
  
A calculadora de capacidade do [Skype for Business server 2015](https://www.microsoft.com/download/details.aspx?id=51196) e o [Skype for Business Server 2019 de capacidade](https://www.microsoft.com/download/details.aspx?id=57509) aumentam a [ferramenta de planejamento do Skype for Business](https://www.microsoft.com/download/details.aspx?id=50357) e sua documentação de implantação ([planejar a implantação do Skype for Business Server 2015](../plan-your-deployment/plan-your-deployment.md) e planejar a implantação do [Skype for Business 2019 Server](../../SfBServer2019/plan/plan-your-deployment-2019.md) , respectivamente). Use a calculadora após revisar o guia e criar uma topologia recomendada usando a ferramenta de planejamento.
  
A calculadora de capacidade do Skype for Business Server ajuda a determinar os requisitos do servidor com base no número de usuários e nas ferramentas de comunicação que sua organização usa. Depois de determinar o perfil do usuário e as funções que você deseja habilitar para os usuários, use a calculadora para determinar o número de servidores, memória e largura de banda que você precisará. Esta versão da calculadora não fornece orientações para os requisitos de e/s de disco.
  
Você pode aproveitar a maior parte da calculadora se tiver informações precisas e detalhadas sobre seu perfil de usuário específico. Por exemplo, a porcentagem de usuários habilitados para voz, média de chamadas por usuário por hora, duração da chamada e a porcentagem de usuários simultâneos em conferências podem fazer uma grande diferença nos requisitos do servidor. A precisão das recomendações criadas pela calculadora depende da precisão das informações que você fornece.
  
Depois de usar a ferramenta de planejamento e a calculadora de planejamento de capacidade, você deve simular sua carga proposta e planejada para garantir que o Skype for Business Server seja adequadamente provisionado. Para realizar testes de estresse sob uma carga simulada, use a [ferramenta de stress and performance do Skype for Business Server](https://www.microsoft.com/download/details.aspx?id=50367) , documentada na [ferramenta de estresse e desempenho do Skype for Business Server](https://technet.microsoft.com/library/mt631400.aspx).
  
## <a name="using-the-capacity-calculator"></a>Usando a calculadora de capacidade

A calculadora é uma planilha do Microsoft Excel. Suas células de entrada são cores laranjas. Os valores padrão são inseridos nas células (para o Skype for Business Server 2015, 80.000 usuários em um pool com doze servidores front-end, enquanto para o Skype for Business Server 2019, 106.000 Users em um pool com dezesseis servidores front-end), mas você deve alterar esses valores para atender às necessidades da sua organização.
  
O modelo de uso contém as seções a seguir. Para calcular os requisitos de capacidade, insira os dados conforme descrito começando na parte superior da planilha e trabalhando linha por linha: 
  
 **Mensagens instantâneas e presença**
  
- Em **número de usuários**, digite o número de usuários que serão conectados ao mesmo tempo. Esse número geralmente é de 80% do número total de usuários provisionados. Na maioria das situações, 100% de seus usuários simultâneos serão habilitados para IM e presença. O padrão é 80.000 para o Skype for Business Server 2015 e 106.000 users for Skype for Business Server 2019.
    
- **Número médio de contatos na lista de contatos** indica o número de contatos que estamos usando para validar os requisitos do sistema. Esse número é fixo e não é algo que você deve alterar.
    
  **Enterprise Voice**
  
- Em **usuários habilitados para o Enterprise Voice**, digite a porcentagem de seus usuários habilitados para o Enterprise Voice. O padrão é 60%. 
    
- Em **número médio de chamadas por usuário por hora (pico)**, digite o número de chamadas por hora que você espera que o usuário médio participe durante horários de carga de pico. O padrão é 4. 
    
- Em **porcentagem de chamadas que usam bypass de mídia**, digite a porcentagem de chamadas feitas por seus usuários que irão ignorar o servidor de mediação. O padrão é 65%, mas pode ser menor se você estiver espalhado geograficamente ou tiver uma grande porcentagem de usuários que trabalham de casa.
    
- Em **porcentagem de usuários de voz envolvidos nas chamadas UC-PSTN**, digite a porcentagem das chamadas da sua organização que são chamadas telefônicas UC-PSTN. O padrão é 60%.
    
- **Porcentagem de usuários de voz envolvidos nas chamadas UC-UC** mostra a porcentagem de usuários que estão habilitados para o Enterprise Voice que serão habilitados apenas para as chamadas UC-UC. Esse número é calculado com base no que você insere para **porcentagem de usuários de voz habilitados para chamadas UC-PSTN**. 
    
  **Conferências**
  
- Em **porcentagem de usuários em conferências simultâneas**, digite a porcentagem de usuários que farão parte de conferências ao mesmo tempo. O padrão é 5%. 
    
- Em **porcentagem de conferências com somente im de grupo (sem voz)**, digite a porcentagem de conferências que envolverão apenas mensagens instantâneas e que não incluem áudio. O padrão é 10%
    
- Em **porcentagem de usuários que usam conferência discada**, digite a porcentagem de participantes em conferências que usarão conferência discada ao mesmo tempo. O padrão é 15%.
    
- Em **porcentagem de conferências usando voz**, digite a porcentagem de conferências que incluirão áudio. 
    
  - Se 20% de suas conferências de voz também incluirem vídeo normal, marque a caixa de seleção **incluindo vídeo (sem exibição múltipla)** .
    
  - Se 20% de suas conferências também incluir vídeo de várias exibições, marque a caixa de seleção **incluir vários modos de exibição** .
    
  - Se 50% de suas conferências de voz também incluem compartilhamento de aplicativo, marque a caixa de seleção **incluir compartilhamento de aplicativo** .
    
  - Se 20% de suas conferências de voz incluírem carregamentos de dados, como apresentações do PowerPoint, marque a caixa de seleção **incluir Webconferência** .
    
  **Movimentação**
  
- Em **porcentagem de usuários habilitados para mobilidade**, digite a porcentagem de seus usuários que serão habilitados para se conectarem ao Skype for Business Server usando dispositivos móveis. O padrão é 40%. 
    
Quando você inserir todas as informações necessárias, a calculadora de capacidade estimará suas necessidades. As células amarelas mostram valores calculados para requisitos de CPU, memória e largura de banda com base nos testes executados nos laboratórios de desempenho do Skype for Business Server. Os números são fornecidos como uma diretriz, nem cada única variação é testada e validada. Os seguintes valores são calculados: 
  
- **CPU de front end**: porcentagem de uso da CPU se a carga inteira estivesse sendo manipulada por um servidor front-end das mesmas especificações que o servidor usado no teste (consulte a descrição no final deste artigo).
    
- **Rede em Mbps**: requisitos de largura de banda em megabits por segundo (Mbps) para a carga de trabalho correspondente.
    
- **Memória em GB**: memória necessária em GIGABYTES (GB) para a carga de trabalho correspondente.
    
As células verdes mostram recomendações para o modelo de uso inserido. 
  
- **Total de servidores front-end**: o número de servidores físicos necessários é baseado em servidores dedicados que executam o Skype for business Server 2015 com processador duplo, um Core-Core, com 2.260 megaciclos ou o Skype for business Server 2019 com o Intel Xeon E5-2673 v3, processador duplo, Hex-Core.
    
    Observe que a habilitação do hyperthreading é recomendada e comprovada para melhorar o desempenho de servidores que oferecem suporte a áudio/vídeo.
    
- **Servidores de borda**: o número de servidores de borda necessários, com base em 30% de todos os usuários simultâneos que estão se comunicando por meio dos servidores de borda. Essa porcentagem não pode ser alterada na calculadora. 
    
- **Repositório de serviços de arquivamento/registro de detalhes de chamada/qualidade da experiência**: o número de repositórios necessários para recursos de arquivamento ou monitoramento, se eles estiverem habilitados em sua organização.
    
- **Servidor de banco de dados back-end necessário (pools necessários)**: o número de servidores de banco de dados back-end necessários para suportar a carga de trabalho selecionada.
    
Além disso, na linha ao lado de total dos servidores front-end, mais informações são fornecidas sobre a carga nos servidores e na rede para todas as cargas de trabalho planejadas combinadas.
  
- **Carga média da CPU**: o uso médio da CPU por servidor de front-end.
    
- **Rede em Mbps**: a alocação de largura de banda necessária para suportar o modelo de uso inserido.
    
- **Memória em GB**: memória, em gigabytes, necessária para cada servidor de front-end.
    
### <a name="adjusting-for-your-processors"></a>Ajustando para seus processadores

Todos os valores de uso da CPU na planilha presumem que cada servidor do Skype for Business Server 2015 tenha um processador duplo, um núcleo hex com 2,26 GHz, pelo menos 32 GB de memória, e 8 ou mais unidades de disco rígido de 10.000 RPM com pelo menos 72 GB de espaço livre em disco. Para cada servidor do Skype for Business Server 2019, todos os valores de uso da CPU na planilha presumem que cada servidor tenha um processador duplo, um Core-core com o Intel Xeon E5-2673 v3, pelo menos 64 GB de memória e 8 ou mais unidades de disco rígido de 10.000-RPM de pelo menos 72 GB livres de discos aprendizado.
  
Se seus servidores tiverem processadores diferentes, você poderá ajustar os números para que correspondam ao seu hardware.
  
