---
title: Planejamento de capacidade do Skype for Business Server 2019
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: ''
description: Os tópicos desta seção ajudam a entender como planejar e implantar o Skype for Business Server para que você possa planejar adequadamente o número de usuários em sua organização e planejar a carga do servidor que suas atividades geram.
ms.openlocfilehash: 15f59d2052a4d73f6e1b1c09b10525b503958fea
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824025"
---
# <a name="capacity-planning-for-skype-for-business-server-2019"></a>Planejamento de capacidade do Skype for Business Server 2019

Este artigo fornece orientação sobre quantos servidores você precisa em um site para o número de usuários nesse site, de acordo com o uso descrito em [modelos de usuário no Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md)

## <a name="tested-hardware-platform"></a>Plataforma de hardware testada

Fizemos os testes de desempenho no hardware descrito na tabela abaixo. Todas as nossas recomendações e resultados são baseados neste hardware. Se você decidir usar hardware menos potente do que o listado aqui, lembre-se de que você pode enfrentar problemas na funcionalidade ou baixo desempenho.

**Hardware usado em testes de desempenho**

|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Processador Intel Xeon E5-2673 v3 dual, 6 núcleo, 2,4 gigahertz (GHz) ou superior.  <br/> Os processadores Intel Itanium não são compatíveis com as funções do Skype for Business Server 2019.  <br/> |
|Memória  <br/> |32 gigabytes (GB).  <br/> |
|Disco  <br/> |UMA DESTAS OPÇÕES:  <br/> • 8 ou mais 10000 unidades de disco rígido RPM com pelo menos 72 GB de espaço livre em disco (dois discos usando RAID 1 e 6 usando RAID 10).  <br/> OR  <br/> • Os discos de estado sólido (SSDs) podem fornecer o mesmo espaço livre e desempenho semelhante para os drives de disco mecânico 8 10000 RPM.  <br/> |
|Rede  <br/> |1 adaptador de rede duplo, 1 Gbps ou superior (2 adaptadores de rede podem ser usados, mas eles precisam estar combinados com um único endereço MAC e um único endereço IP).  <br/> **Não** há suporte para configurações de duas ou várias bases para servidores front-end, servidores back-end e servidores Standard Edition. <br/> Desde que não estejam expostos ao sistema operacional e estejam sendo usados para monitorar e gerenciar o hardware do servidor, você pode ter sistemas de gerenciamento fora de banda, como o DRAC ou o ILO. Esse cenário não constitui um servidor multihomed e tem suporte.  <br/> |

## <a name="summary-of-results"></a>Resumo de Resultados

A tabela a seguir resume nossas recomendações.

|**Função de servidor**|**Número máximo de usuários suportados**|
|:-----|:-----|
|Pool de front-ends com dezesseis servidores front-end e servidor back-end ou um par de servidores back-end com SQL sempre ativado para alta disponibilidade.  <br/> |106.000 usuários exclusivos conectados simultaneamente, mais 50% de vários pontos de presença (MPOP) que representam instâncias não móveis, além de 40% dos usuários habilitados para mobilidade para um total de pontos de extremidade 210.000.  <br/> |
|Conferência A/V  <br/> |O serviço de conferência A/V fornecido por um pool de front-end oferece suporte a conferências do pool presumindo um tamanho máximo de conferência de usuários do 250, e apenas uma dessas grandes conferências sendo executadas ao mesmo tempo.  <br/> **Observação:** Além disso, você pode dar suporte a conferências grandes de usuários do 250 e do 1000 implantando um pool de front-end separado com dois servidores front-end para hospedar as conferências grandes. Para obter detalhes, consulte [planejar reuniões grandes no Skype for Business Server](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md). <br/> |
|Um servidor de borda  <br/> |18.000 usuários remotos simultâneos.  <br/> |
|Um diretor  <br/> |18.000 usuários remotos simultâneos.  <br/> |
|Monitoramento e Arquivamento  <br/> |Os serviços de front-end de monitoramento e arquivamento são executados em cada servidor front-end, em vez de usar funções de servidor separadas.  <br/> O monitoramento e arquivamento ainda exigem seus próprios armazenamentos de banco de dados. Se você também tiver o Exchange 2013 ou posterior, poderá manter seus dados de arquivamento no Exchange, em vez de em um banco de dados SQL dedicado.  <br/> |
|Um servidor de mediação  <br/> |O servidor de mediação colocado no front-end Server é executado em cada servidor front-end em um pool e deve fornecer capacidade suficiente para os usuários do pool. Para o servidor de mediação autônomo, consulte a seção "servidor de mediação" mais adiante neste tópico.  <br/> |
|Um servidor Standard Edition  <br/> |É altamente recomendável que, se você usar os servidores de edição padrão para hospedar usuários, sempre use dois servidores, emparelhados usando as recomendações de [planejamento para alta disponibilidade e recuperação de desastres](https://technet.microsoft.com/library/15a72073-0336-45dd-b2a0-35e7522c6000.aspx). Cada servidor no par pode hospedar até 2.500 usuários e, se um servidor falhar, o servidor restante poderá dar suporte a 5.000 usuários em um cenário de falha.  <br/>  Se sua implantação inclui um quantidade de tráfego significativa de áudio ou vídeo, o desempenho do servidor pode ser prejudicado com mais de 2.500 usuários por servidor. Nesse caso, você deve considerar adicionar mais servidores de edição padrão ou mover para o Skype for Business Server Enterprise Edition. <br/> |

## <a name="front-end-server"></a>Servidor Front-End

> [!NOTE]
> Pools alongados não são suportados pela função desse servidor.

Em um pool de front-ends, você deve ter um servidor front-end para todos os usuários do 6.660 hospedados em seu pool, pressupondo que a hipersegmentação esteja habilitada em todos os servidores do pool, que você esteja usando o SQL Server Express Edition e que o hardware do servidor atenda às recomendações dos [requisitos do servidor para o Skype for Business Server 2019](system-requirements.md). O número máximo de usuários em um pool de front-ends é o 106.000, pressupondo que o hyperthreading esteja habilitado e o SQL Server Express Edition seja usado em todos os servidores do pool. Se você tiver mais de 106.000 usuários em um site, poderá implantar mais de um pool de front-end.

Quando você conta com o número de usuários em um pool Front-end, inclua qualquer usuário hospedado em aparelhos de ramificação sobreviventes e servidores de ramificação sobreviventes em filiais que estão associados a este pool de front-ends.

Quando um servidor ativo está indisponível, suas conexões são transferidas automaticamente para outros serviços no pool. Em um cenário em que você tenha usuários do 30.000 e cinco servidores front-end, se um servidor estiver indisponível, as conexões do 6000 de seus usuários precisam ser transferidas para seus outros quatro servidores restantes. Os quatro servidores restantes terão 7.500 usuários cada, o que é um número maior que o recomendado.

Se, em vez disso, você começou com seis servidores front end para seus usuários do 30.000 e um estiver indisponível, um total de 5000 usuários precisarão mover para os cinco servidores restantes. Cada um desses cinco servidores hospedará 6.000 usuários, que é o âmbito recomendado.

O número máximo de usuários em um pool de front-ends é 106.000. O número máximo de servidores front-end em um pool é 16.

Para um pool de front-ends com usuários do 80.000, 16 servidores front-end funcionarão para desempenho em implantações típicas que seguem os [modelos de usuário do Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md). Implantações projetadas para dar suporte a failover de recuperação de desastres presumindo que um máximo de 53.000 usuários podem ser hospedados em cada um dos dois pools front-ends emparelhados, em que cada pool tenha servidores front-end suficientes para conter os usuários em ambos os pools, deve haver falha em um pool com t o outro.

O número de usuários com suporte com bom desempenho por parte de um pool de front-end específico pode ser diferente dos seguintes números pelos seguintes motivos:

- O hardware para seus servidores front-ends não atende às recomendações.
- Em vez de usar o SQL Server Express Edition, você pode usar outra edição do SQL Server, que pode ser capaz de hospedar usuários adicionais em cada pool de front-ends.
- O uso da sua organização é muito diferente dos modelos de usuário, por exemplo, se você tiver muito mais tráfego de conferência.

A tabela a seguir mostra a média de largura de banda para IM e presença, considerando o modelo de usuário, conforme definido nos [modelos de usuário do Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md).

|**Largura de banda média por usuário**|**Requisitos de largura de banda por servidor front-end com usuários do 6.660**|
|:-----|:-----|
|3 a 3,75 KBps  <br/> |13 MBps  <br/> |

> [!NOTE]
> Para melhorar o desempenho de mídia da funcionalidade co-localizado de conferência e servidor de mediação em seus servidores front-end, você deve habilitar o RSS (dimensionamento de recebimento) nos adaptadores de rede em seus servidores front-end. O RSS permite que pacotes de entrada sejam tratados paralelamente por vários processadores no servidor. Para obter detalhes, consulte [RSS (receber dimensionamento à vista) na documentação do Windows Server 2012](https://go.microsoft.com/fwlink/p/?LinkId=620365). Para obter detalhes sobre como ativar RSS, consulte a documentação do seu adaptador de rede.

## <a name="conferencing-maximums"></a>Máximos de Conferência

Devido ao modelo de usuário de que 5% dos usuários em um pool pode estar em uma conferência a qualquer momento, um pool de usuários do 106.000 pode ter cerca de 5.300 usuários em conferências simultaneamente. Espera-se que essas conferências sejam uma mistura de mídias (algumas somente IM, algumas IM com áudio, algumas áudio/vídeo, por exemplo) e de número de participantes. Não existe um limite rígido para o número real de conferências permitidas e o uso real determina o desempenho real. Por exemplo, se a sua organização tiver muitas outras conferências de modo misto do que são presumidas no modelo de usuário, talvez seja necessário implantar mais servidores front-end ou servidores de conferência A/V do que as recomendações encontradas neste artigo. Para obter detalhes sobre as suposições no modelo de usuário, consulte [modelos de usuário no Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md).

O tamanho máximo de conferência compatível hospedado por um pool de front-end normal do Skype for Business Server que também hospeda usuários é o 250 participantes. Enquanto esta conferência de 250 usuários está acontecendo, o pool ainda suporta outras conferências, de forma que 5% dos usuários do pool estão em conferências simultâneas. Por exemplo, em um pool de 16 servidores front-end e usuários do 106.000, enquanto a conferência de usuário do 250 está acontecendo, o Skype for Business Server oferece suporte a 5.050 outros usuários que participam de conferências menores.

Independentemente do número de usuários hospedados no pool de front-ends ou no servidor Standard Edition, o Skype for Business Server oferece suporte a um mínimo de 125 outros usuários que participam de conferências menores no mesmo pool ou servidor que hospeda uma conferência do 250 para o usuário.

Para habilitar as conferências que têm entre os usuários do 250 e do 1000, você pode configurar um pool de front-end separado apenas para hospedar essas conferências. Este pool de front-ends não hospeda usuários. Para obter detalhes, consulte [plano para reuniões grandes no Skype for Business Server](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md).

Se a sua organização tiver muito mais conferências de modo misto do que são presumidas no modelo de usuário, talvez seja necessário implantar mais servidores front-end do que a recomendação deste documento (até um limite de 16 servidores front-end). Para obter detalhes sobre as suposições no modelo de usuário, consulte [modelos de usuário no Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md).

## <a name="edge-server"></a>Servidor de Borda

> [!NOTE]
> Pools alongados não são suportados pela função desse servidor.

Você deve implantar um servidor de borda para cada um dos usuários remotos do 18.000, que acessarão um site simultaneamente. Recomendamos, no mínimo, dois servidores de borda para alta disponibilidade. Essas recomendações pressupõem que o hardware para seus servidores de borda atenda às recomendações nas [plataformas de hardware do servidor](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

Quando você conta com o número de usuários para os servidores de borda, inclua os usuários hospedados em aparelhos de ramificação sobreviventes e servidores de ramificação sobreviventes em filiais que estão associados a um pool de front-ends neste site.

> [!NOTE]
> Para melhorar o desempenho do serviço de borda de conferência A/V em seus servidores de borda, você deve habilitar o recurso de dimensionamento de recebimento (RSS) nos adaptadores de rede dos servidores de borda. O RSS permite que pacotes de entrada sejam tratados paralelamente por vários processadores no servidor. Para obter detalhes, marque a opção [RSS (Receive Side Scaling) no Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731). Para obter detalhes sobre como ativar RSS, consulte a documentação do seu adaptador de rede.

## <a name="director"></a>Diretor

> [!NOTE]
> Pools alongados não são suportados pela função desse servidor.

Se você implantar a função de servidor diretor, recomendamos implantar um director para cada um dos usuários remotos do 18.000 que acessarão um site simultaneamente. Recomendamos, no mínimo, dois diretores para alta disponibilidade. Essas recomendações pressupõem que o hardware para seus servidores de borda atenda às recomendações nas [plataformas de hardware do servidor](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

Quando você conta com o número de usuários para os directors, inclua os usuários hospedados em aparelhos de ramificação sobreviventes e servidores de ramificação sobreviventes em filiais que estão associados a um pool de front-end neste site.

## <a name="mediation-server"></a>Servidor de Mediação

> [!NOTE]
> Pools alongados não são suportados pela função desse servidor.

Se você colocar o servidor de mediação com servidor front-end, o servidor de mediação será executado em todos os servidores front-end do pool e deve fornecer capacidade suficiente para os usuários do pool.

Se você implantar um pool autônomo do servidor de mediação, o número de servidores de mediação a serem implantados depende de muitos fatores, incluindo o hardware usado para o servidor de mediação, o número de usuários de VoIP que você tem, o número de pares de gateways que cada pool de servidores de mediação controles, o tráfego de horas ocupados por meio desses gateways e a porcentagem de chamadas com mídia que ignora o servidor de mediação.

As tabelas a seguir fornecem uma diretriz para quantas chamadas simultâneas um servidor de mediação pode manipular, pressupondo que o hardware dos servidores de mediação atenda aos requisitos nas [plataformas de hardware do servidor](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx) e que o hyperthreading esteja habilitado. Para obter detalhes sobre a escalabilidade do servidor de mediação, consulte [estimando o uso e o tráfego de voz do Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/estimating-voice-traffic.md) e [diretrizes de implantação do servidor de mediação do Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/mediation-server-deployment-guidelines.md).

Todas as tabelas a seguir consideram o uso resumido nos [modelos de usuário do Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md).

**Capacidade autônoma do servidor de mediação: 70% usuários internos, 30% usuários externos com capacidade de chamada não ignorada (transcodificação de mídia realizada pelo servidor de mediação)**

|**Hardware de servidor**|**Número máximo de chamadas**|**Número máximo de linhas T1**|**Número máximo de linhas E1**|
|:-----|:-----|:-----|:-----|
|Processador Intel Xeon E5-2673 v3 dual, 6 núcleo, 2,4 gigahertz (GHz) ou superior **com hiperthreading desabilitado**, com memória de 64 GB e uma placa de adaptador de rede de duas portas.  <br/> |1500  <br/> |64  <br/> |49  <br/> |
|Processador Intel Xeon E5-2673 v3 dual, 6 núcleo, 2,4 gigahertz (GHz) ou superior, com memória de 64 GB e uma placa de adaptador de rede de duas portas.  <br/> |2000  <br/> |88  <br/> |66  <br/> |

> [!NOTE]
> Embora os servidores com 64 GB de memória sejam usados para teste de desempenho, os servidores com 32 GB de memória são compatíveis com o servidor de mediação autônomo e são suficientes para fornecer o desempenho mostrado nesta tabela.

**Capacidade do servidor de mediação (servidor de mediação posicionado com servidor front-end) 70% usuários internos, 30% usuários externos, capacidade de chamada sem bypass (processamento de mídia executado pelo servidor de mediação)**

|**Hardware de servidor**|**Número máximo de chamadas**|
|:-----|:-----|
|Processador Intel Xeon E5-2673 v3 dual, 6 núcleo, 2,4 gigahertz (GHz) ou superior., com memória de 64 GB e 2 placas de adaptador de rede de 1 GB.  <br/> |200  <br/> |

> [!NOTE]
> Esse número é muito menor do que os números do servidor de mediação autônomo. Isso se deve ao fato de o servidor front-end ter que manipular outros recursos e funções para os usuários do 6600 hospedados nele, além da transcodificação necessária para chamadas de voz.

> [!NOTE]
> Para melhorar o desempenho do servidor de mediação, você deve habilitar o RSS (escala de recebimento) nos adaptadores de rede em seus servidores de mediação. O RSS permite que pacotes de entrada sejam tratados paralelamente por vários processadores no servidor. Para obter detalhes, consulte "[dimensionamento do lado de recebimento no Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731)". Para obter detalhes sobre como ativar RSS, consulte a documentação do seu adaptador de rede.

## <a name="back-end-server"></a>Servidor Back-End

Embora grande parte das informações do banco de dados seja armazenada principalmente nos servidores de front-end, você deve verificar se seus servidores de back-end atendem às recomendações de hardware listadas anteriormente nesta seção e em [plataformas de hardware de servidor](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

Para fornecer alta disponibilidade de seu servidor back-end, recomendamos implantar os grupos de disponibilidade AlwaysOn ou o espelhamento do servidor. Para obter mais informações, consulte [Back End Server high availability in Skype for Business Server](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

## <a name="monitoring-and-archiving"></a>Monitoramento e Arquivamento

Se você implantar o monitoramento ou o arquivamento, a funcionalidade de front-end desses serviços é executada nos servidores de front-end, monitoramento e arquivamento cada um deles usa seu próprio repositório de banco de dados, separado da loja back-end. Como alternativa, se você tiver o Exchange 2013 implantado, poderá armazenar dados de arquivamento de mensagens instantâneas no Exchange em vez de em um repositório SQL dedicado.

A tabela a seguir indica aproximadamente quanto armazenamento de banco de dados é exigido por usuário, por dia, para os dados de monitoramento e arquivamento.

||**CDR (Monitoramento)** <br/> |**QoE (Monitoramento)** <br/> |**Archiving** <br/> |
|:-----|:-----|:-----|:-----|
|Espaço em disco exigido por usuário, por dia  <br/> |49 KB  <br/> |28 KB  <br/> |57 KB  <br/> |

A Microsoft usou o hardware na tabela a seguir para p servidor de banco de dados para monitoramento e arquivamento durante seus testes de desempenho. O teste coletou os dados de dois pools de front-end, cada um contendo 80.000 usuários.

**Hardware usado nos testes de desempenho de monitoramento e arquivamento**

|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Processador Intel Xeon E5-2673 v3 dual, 6 núcleo, 2,4 gigahertz (GHz) ou superior.  <br/> |
|Memória  <br/> |48 GB  <br/> |
|Disco  <br/> | UMA DESTAS OPÇÕES:<br/> • 4 ou mais 10000 unidades de disco rígido RPM com pelo menos 72 GB de espaço livre em disco (os discos devem estar em uma configuração RAID 1 2x). <br/>OR <br/>• Os discos de estado sólido (SSDs) podem fornecer o mesmo espaço livre e desempenho semelhante para os drives de disco mecânico 4 10000 RPM.   <br/> |
|Rede  <br/> | 1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 recomendados, que exige agrupamento com um único endereço MAC e um único endereço IP).  <br/> |

**Configurações de disco recomendadas**

|**Unidade** <br/> |**Configuração RAID** <br/> |**Número de discos** <br/> |
|:-----|:-----|:-----|
|CDR, QoE e arquivos de banco de dados de arquivamento, em uma única unidade  <br/> |1+0  <br/> |16  <br/> |
|Arquivo de log do banco de dados de CDR  <br/> |1  <br/> |2  <br/> |
|Arquivo de log do banco de dados de QoE  <br/> |1  <br/> |2  <br/> |
|Arquivo de log do banco de dados de arquivamento  <br/> |1  <br/> |2  <br/> |

## <a name="video-interop-server-capacity"></a>Capacidade do servidor de interoperabilidade de vídeo

Se você implantar o servidor de interoperabilidade de vídeo e precisar determinar a capacidade, examine o número máximo de sistemas de teleconferência de vídeo (VTCs) que estarão em chamadas simultâneas. Por exemplo, se você tiver 250 VTCs em sua organização e o seu modelo de usuário estima que no máximo, 20% delas podem estar em chamadas simultâneas, você baseará seu planejamento de capacidade em 50 VTCs simultâneas.

