---
title: Calculadora de planejamento de capacidade do Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/1/2018
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: 'Resumo: como usar a Ferramenta Calculadora de Capacidade.'
ms.openlocfilehash: bdf3437ab044b7081d1f9f0ccb5ffa41a41e1545
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33914930"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a>Calculadora de planejamento de capacidade do Skype for Business Server
 
**Resumo:** como usar a Ferramenta Calculadora de Capacidade.

> [!NOTE]
> Este artigo faz referência Skype para Business Server 2015 downloads, mas ela se aplica ao:
> - Skype para Business Server 2019.
> - Skype para Business Server 2015.
  
O [Skype para Calculadora de capacidade do Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=51196) e [Skype para Calculadora de capacidade do Business Server 2019](https://www.microsoft.com/en-us/download/details.aspx?id=57509) incrementar o [Skype para a ferramenta de planejamento de negócios](https://www.microsoft.com/en-us/download/details.aspx?id=50357) e a documentação de implantação ([planejar sua Skype para negócios Implantação de servidor 2015](../plan-your-deployment/plan-your-deployment.md) e [planejar seu Skype para implantação Business Server 2019](../../SfBServer2019/plan/plan-your-deployment-2019.md) respectivamente). Use a calculadora após ter revisado o guia e criado uma topologia recomendada usando a Ferramenta de Planejamento.
  
O Skype referente a Calculadora de capacidade do Business Server ajuda a determinar os requisitos de servidor com base no número de usuários e as ferramentas de comunicação que sua organização usa. Após ter determinado o perfil do usuário e as funções que você deseja habilitar para seus usuários, use a calculadora para determinar o número de servidores, a memória e a largura de banda necessários. Esta versão da calculadora não fornece orientação quanto às exigências de E/S do disco.
  
Você poderá aproveitar grande parte da calculadora se tiver informações precisas e detalhadas sobre seu perfil do usuário específico. Por exemplo, a porcentagem dos usuários de voz, chamadas médias por usuário e por hora, duração da chamada e porcentagem dos usuários simultâneos em conferências podem fazer uma diferença enorme nas exigências do servidor. A precisão das recomendações criadas pela calculadora depende da precisão das informações fornecidas.
  
Depois que você tiver usado a ferramenta de planejamento e a Calculadora de planejamento de capacidade, você deve simular sua carga proposta e planejada para garantir que Skype para Business Server será provisionado adequadamente. Para executar o teste sob uma carga de simulação de carga de, use o [Skype para ferramenta de desempenho e estresse do Business Server](https://www.microsoft.com/en-us/download/details.aspx?id=50367) documentados em [Skype para ferramenta de desempenho e estresse do Business Server](https://technet.microsoft.com/en-us/library/mt631400.aspx).
  
## <a name="using-the-capacity-calculator"></a>Usando a capacidade da calculadora

A calculadora é uma planilha do Microsoft Excel. As células de entrada estão na cor laranja. Valores padrão são inseridos nas células (para Skype para Business Server 2015, 80.000 usuários em um pool com doze servidores Front-End, enquanto para Skype para Business Server 2019, 106.000 usuários em um pool com dezesseis servidores Front-End), mas você deve alterar esses valores para corresponde as necessidades da sua organização.
  
O modelo de uso contém as seguintes seções. Para calcular as exigências de sua capacidade, digite os dados conforme descrito começando pela parte superior da folha e trabalhando linha a linha: 
  
 **Mensagem instantânea e presença**
  
- Em **Número de usuários**, digite o número de usuários que estarão conectados simultaneamente. Esse número normalmente é 80% do número total de usuários provisionados. Na maioria das situações, 100% de seus usuários simultâneos estarão ativados para mensagens instantâneas e presença. O padrão é 80.000 para Skype para Business Server 2015 e 106.000 usuários para Skype para Business Server 2019.
    
- **Número médio de contatos na lista Contatos** indica o número de contatos que nós estamos usando para validar as exigências de seu sistema. Esse número não muda.
    
  **Enterprise Voice**
  
- Em **Usuários permitidos para o Enterprise Voice**, digite a porcentagem de seus usuários que têm permissão para o Enterprise Voice. O padrão é 60%. 
    
- Em **Número médio de chamadas por usuário e por hora (pico)**, digite o número de chamadas por hora que você espera que o usuário médio participe durante as horas de pico da carga. O padrão é 4. 
    
- Em **Porcentagem de chamadas que usam o bypass de mídia**, digite a porcentagem de chamadas feitas por seus usuários que ignorará o Servidor de Mediação. O padrão é 65%, mas poderia ser menor se você estivesse espalhado geograficamente ou se tivesse uma porcentagem maior de usuários que trabalham de sua casa.
    
- Em **porcentagem de usuários de voz envolvidos em chamadas UC-PSTN**, digite a porcentagem de chamadas da sua organização que são chamadas de telefone UC-PSTN. O padrão é 60%
    
- Em **Porcentagem de usuários de voz envolvidos nas chamadas UC-UC**, mostra a porcentagem de usuários que são ativados para o Enterprise Voice e que serão ativados apenas para as chamadas UC-UC. Esse número é calculado com base no que você digita para a **Porcentagem de usuários de voz ativados para as chamadas UC-PSTN**. 
    
  **Conferências**
  
- Em **Porcentagem de usuários em conferências simultâneas**, digite a porcentagem de usuários que participarão simultaneamente em conferências. O padrão é 5%. 
    
- Em **Porcentagem de conferências com MI de grupo apenas (sem voz)**, digite a porcentagem de conferências que envolverão apenas a mensagem instantânea e não inclui áudio. O padrão é 10%
    
- Em **Porcentagem de usuários usando conferência discada**, digite a porcentagem de participantes nas conferências que usarão a conferência discada. O padrão é 15%.
    
- Em **Porcentagem de conferências usando voz**, digite a porcentagem de conferências que incluirão áudio. 
    
  - Se 20% das conferências de voz incluírem também um vídeo normal, marque a caixa de seleção **Incluir vídeo (sem Multi-View)**.
    
  - Se 20% de suas conferências incluírem o vídeo Multi-View, marque a caixa de seleção **Incluir Multi-View**.
    
  - Se a 50% de suas conferências de voz também incluirá o compartilhamento de aplicativos, marque a caixa de seleção **incluindo compartilhamento de aplicativos** .
    
  - Se 20% de suas conferências de voz incluírem uploads de dados, como as apresentações do PowerPoint, marque a caixa de seleção **Incluir conferência da Web**.
    
  **Mobilidade**
  
- Em **porcentagem de usuários ativados para mobilidade**, digite a porcentagem dos usuários que será habilitado para conectar Skype para Business Server usando dispositivos móveis. O padrão é 40%. 
    
Quando você tiver digitado todas as informações necessárias, a calculadora de capacidade estimará as exigências. As células amarelas mostram valores calculados para CPU, memória e requisitos de largura de banda com base nos testes executados no Skype para os laboratórios de desempenho de servidor de negócios. Os números são fornecidos como uma diretriz e nem toda variação é testada e validada. Os seguintes valores são calculados: 
  
- **CPU de front-end**: a porcentagem de uso da CPU se a carga inteira estava sendo lidada por um servidor de front-end com as mesmas especificações do servidor que foi usado no teste (veja a descrição no final deste artigo).
    
- **Rede em Mbps**: as exigências da largura de banda em megabits por segundo (Mbps) para a carga de trabalho correspondente.
    
- **Memória em GB**: a memória requerida em gigabytes (GB) para a carga de trabalho correspondente.
    
As células verdes mostram as recomendações para o modelo de uso inserido. 
  
- **Servidores Front-End total**: O número de servidores físicos necessários baseiam-se em servidores dedicados executando Skype para Business Server 2015 com processador duplo, hex-core, com 2,260 megaciclos ou Skype para Business Server 2019 com Intel Xeon E5-2673 v3, dual processador, hex-core.
    
    Note que é recomendado ativar o hyperthreading e foi comprovado que melhora o desempenho para os servidores que suportam áudio/vídeo.
    
- **Servidores de borda**: o número de Servidores de borda requeridos, com base em 30% de todos os usuários simultâneos comunicando-se por meio dos Servidores de borda. Essa porcentagem não pode ser alterada na calculadora. 
    
- **Armazenamento de serviços de Arquivamento/Registro de detalhes da camada/Qualidade da experiência**: o número de armazenamentos requeridos para os recursos de Arquivamento ou Monitoramento, se estiverem ativados em sua organização.
    
- **Servidor requerido do banco de dados de back-end (pools requeridos)**: o número de servidores do banco de dados de back-end requeridos para suportar a carga de trabalho selecionada.
    
E mais, na linha próxima de 'Servidores de front-end totais, mais informações são fornecidas sobre a carga em seus servidores e rede para todas as cargas de trabalho planejadas e combinadas.
  
- **Carga média da CPU**: o uso médio da CPU por servidor de front-end server.
    
- **Rede em Mbps**: a alocação da largura de banda requerida para suportar o modelo de uso fornecido.
    
- **Memória em GB**: a memória, em gigabytes, requerida para cada servidor de front-end server.
    
### <a name="adjusting-for-your-processors"></a>Ajustando para seus processadores

Todos os números de utilização de CPU na planilha pressupõem que cada Skype para Business Server 2015 server possui um processador duplo, hex-core com 2,26 GHz, pelo menos 32 GB de memória, e unidades de disco rígido 8 ou mais de 10.000 RPM com pelo menos 72 GB Libere espaço em disco. Para cada Skype para Business Server 2019 server, todos os números de utilização de CPU na planilha pressupõem que cada servidor tem um processador duplo, hex-core com Intel Xeon E5-2673 v3, pelo menos 64 GB de memória, e unidades de disco rígido 8 ou mais de 10.000 RPM com pelo menos 72 GB livre s de disco ritmo.
  
Se seus servidores tiverem processadores diferentes, você poderá ajustar os valores para corresponderem ao seu hardware.
  
