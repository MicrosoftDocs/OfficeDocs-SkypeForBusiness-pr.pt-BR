---
title: Planejamento de capacidade uso de modelo de usuário do Skype para Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
description: Este artigo fornece orientação sobre quantos servidores são necessários em um site para o número de usuários neste site, de acordo com o uso descrito em modelos de usuário Skype for Business Server.
ms.openlocfilehash: 3a1838200e4590649fd290530a50fba3015b670f
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23261599"
---
# <a name="capacity-planning-user-model-usage-for-skype-for-business-server"></a>Planejamento de capacidade uso de modelo de usuário do Skype para Business Server

Este artigo fornece orientação sobre quantos servidores são necessários em um site para o número de usuários neste site, de acordo com o uso descrito em [modelos de usuário Skype para Business Server](user-models.md).

> [!NOTE]
> Todas as recomendações neste artigo presumem que você tenha instalado a Atualização Cumulativa do Skype for Business, de novembro de 2015, ou posterior, em seus servidores.

## <a name="tested-hardware-platform"></a>Plataforma de hardware testada

Fizemos os testes de desempenho no hardware descrito na tabela abaixo. Todas as nossas recomendações e resultados são baseados neste hardware. Se você decidir usar hardware menos potente do que o listado aqui, lembre-se de que você pode enfrentar problemas na funcionalidade ou baixo desempenho. Estas recomendações de hardware são os mesmos Lync Server 2013, se isso é útil (e em cenários de atualização, pode ser).

**Hardware usado em testes de desempenho**

|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Processador duplo de 64 bits, núcleo hexagonal, 2.26 gigahertz (GHz) ou superior.  <br/> Processadores Intel Itanium não são suportados para Skype para funções de servidor de Business Server.  <br/> |
|Memória  <br/> |32 gigabytes (GB).  <br/> &bull;&nbsp;&nbsp;unidades de disco rígido 8 ou mais de 10.000 RPM com pelo menos 72 GB livre espaço em disco.  <br/> Dois dos discos devem usar RAID 1 e seis devem usar RAID 10.  <br/> - OU -  <br/> &bull;&nbsp;&nbsp;Unidades de estado sólido (SSDs) que fornecem desempenho similar para 8 unidades disco mecânicas de 10.000-RPM.  <br/> |
|Disco  <br/> ||
|Rede  <br/> |&bull;&nbsp;&nbsp;1 adaptador de rede dual-port, 1 Gbps ou superior (2 recomendado, que exige agrupamento com um único endereço MAC e um único endereço IP).  <br/> |

## <a name="summary-of-results"></a>Resumo de Resultados

A tabela a seguir resume nossas recomendações.

|**Função de servidor**|**Número máximo de usuários suportados**|
|:-----|:-----|
|Pool Front-End com doze servidores Front-End e um servidor Back-End ou um par espelhado de servidores Back-End.  <br/> |80.000 usuários únicos, mais 50% de pontos múltiplos de presença (MPOP) representando instâncias não móveis, mais 40% de usuários ativados para mobilidade de um total de 152.000 pontos de extremidade.  <br/> |
|Conferência A/V  <br/> |A / o serviço de conferência V fornecido por um pool de Front-End oferece suporte a conferências do pool supondo um tamanho máximo de conferência de 250 usuários e apenas uma conferência deste tamanho em execução ao mesmo tempo.  <br/> **Observação:** Além disso, você pode suportar conferências grandes de entre 250 e 1.000 usuários Implantando um pool de Front-End separado com dois servidores Front-End para hospedar as conferências grandes. Para obter detalhes, consulte [Planejar para grandes reuniões em Skype para Business Server](../../plan-your-deployment/conferencing/large-meetings.md).  <br/> |
|Um servidor de borda  <br/> |12.000 usuários remotos simultâneos.  <br/> |
|Um diretor  <br/> |12.000 usuários remotos simultâneos.  <br/> |
|Monitoramento e Arquivamento  <br/> |Os monitoramento e arquivamento front-end serviços executados em cada servidor Front-End, em vez de nas funções de servidor separadas.  <br/> O monitoramento e arquivamento ainda exigem seus próprios armazenamentos de banco de dados. Se você também executar o Exchange 2013 ou versões posteriores, você pode manter os dados de arquivamento no Exchange, em vez de um banco de dados dedicado do SQL.  <br/> |
|Um servidor de mediação  <br/> |Servidor de mediação colocado com execuções do servidor Front-End em cada servidor Front-End em um pool e deverá fornecer capacidade suficiente para os usuários no pool. Para o servidor de mediação autônomo, consulte a seção "Servidor de mediação" posteriormente neste tópico.  <br/> |
|Um servidor Standard Edition  <br/> |É altamente recomendável que se você usar servidores Standard Edition para usuários de host, você sempre use dois servidores, juntamente com as recomendações em [Planning for High Availability and Disaster Recovery](https://technet.microsoft.com/library/15a72073-0336-45dd-b2a0-35e7522c6000.aspx). Cada servidor no par pode hospedar até 2.500 usuários e, se um servidor falhar, o servidor restante poderá dar suporte a 5.000 usuários em um cenário de falha.  <br/>  Se sua implantação inclui um quantidade de tráfego significativa de áudio ou vídeo, o desempenho do servidor pode ser prejudicado com mais de 2.500 usuários por servidor. Nesse caso, você deve considerar a adição de mais servidores Standard Edition ou mover para Skype para Business Server Enterprise Edition. <br/> |

## <a name="front-end-server"></a>Servidor Front-End

> [!NOTE]
> Pools alongados não são suportados pela função desse servidor.

Em um pool de Front-End, você deve ter um que servidor Front-End para cada 6,660 usuários hospedado em seu pool, supondo que o hyperthreading está habilitada em todos os servidores do pool e que o hardware de servidor cumpre as recomendações em requisitos de [Server para Skype para Business 2015 de servidor](../requirements-for-your-environment/server-requirements.md) ou [requisitos de sistema do Skype para Business Server 2019](../../../SfBServer2019/plan/system-requirements.md). O número máximo de usuários em um pool de Front-End é novamente 80.000, supondo que o hyperthreading está habilitada em todos os servidores no seu pool. Se você tiver mais de 80.000 usuários em um site, você pode implantar mais de um pool de Front-End.

Ao contar o número de usuários em um pool de Front-End, incluir todos os usuários hospedados em aparelhos de filial persistente e servidores de filial persistente em filiais que estão associados esse pool de Front-End.

Quando um servidor ativo está indisponível, suas conexões são transferidas automaticamente para outros serviços no pool. Em um cenário onde você tinha 30.000 usuários e cinco servidores Front-End, se um servidor não estiver disponível, as conexões de 6000 dos seus usuários precisam ser transferidas para outros quatro servidores restantes. Os quatro servidores restantes terão 7.500 usuários cada, o que é um número maior que o recomendado.

Se em vez disso, você tinha começado com seis servidores Front-End para seus 30.000 usuários e uma fica indisponível, um total de 5.000 usuários necessário mover para cinco servidores restantes. Cada um desses cinco servidores hospedará 6.000 usuários, que é o âmbito recomendado.

O número máximo de usuários de um pool de Front-End é 80.000. O número máximo de servidores em um pool de Front-End é 12.

Para um pool de Front-End com 80.000 usuários, servidores Front-End doze será boas desempenho, em implantações típicas que seguem os [modelos de usuário Skype para Business Server](user-models.md). Projetado para suportar o failover de recuperação de desastre de implantações pressupõem que um máximo de 40.000 usuários pode ser hospedado em cada um dos dois pools de Front-Ends emparelhados, no qual cada pool possui suficiente servidores Front-End para conter os usuários em ambos os pools, deve um pool precisar ser feito um failover t o outro.

O número de usuários suportados com bom desempenho por um determinado pool de Front-End pode diferir desses números pelos seguintes motivos:

- O hardware dos seus servidores Front-End não atender as recomendações.

- Utilização da sua organização é muito diferente dos modelos de usuário, por exemplo, se você tiver o tráfego de webconferência muito mais.

A tabela a seguir mostra a largura de banda média para IM e presença, considerado o modelo de usuário, conforme definido em [modelos de usuário Skype para Business Server](user-models.md).

|**Largura de banda média por usuário**|**Requisitos de largura de banda por servidor Front-End com 6,660 usuários**|
|:-----|:-----|
|1,3 Kpbs  <br/> |13 Mbps  <br/> |

> [!NOTE]
> Para melhorar o desempenho de mídia do co localizado uma / funcionalidade de conferência V e o servidor de mediação em seus servidores Front-End, você deve habilitar receber do lado do dimensionamento (RSS) nos adaptadores de rede em seus servidores Front-End. O RSS permite que pacotes de entrada sejam tratados paralelamente por vários processadores no servidor. Para obter detalhes, consulte [Receber lado dimensionamento (RSS) na documentação do Windows Server 2012](https://go.microsoft.com/fwlink/p/?LinkId=620365). Para obter detalhes sobre como ativar RSS, consulte a documentação do seu adaptador de rede.

## <a name="conferencing-maximums"></a>Máximos de Conferência

Dado o modelo de usuário em que 5% dos usuários em um pool podem estar em uma conferência em qualquer momento, um pool de 80.000 usuários poderia ter cerca de 4.000 usuários em conferências de uma só vez. Espera-se que essas conferências sejam uma mistura de mídias (algumas somente IM, algumas IM com áudio, algumas áudio/vídeo, por exemplo) e de número de participantes. Não existe um limite rígido para o número real de conferências permitidas e o uso real determina o desempenho real. Por exemplo, se sua organização tiver muitas conferências modo misto mais vez pressupõe-se no modelo de usuário, talvez seja necessário implantar mais servidores Front-End ou A / V Conferencing Servers que as recomendações encontrados neste artigo. Para obter detalhes sobre as suposições no modelo de usuário, consulte [modelos de usuário Skype para Business Server](user-models.md).

O tamanho máximo com suporte de conferência hospedado por um Skype regular para o pool de Front End do servidor de negócios que também hospeda usuários é 250 participantes. Enquanto esta conferência de 250 usuários está acontecendo, o pool ainda suporta outras conferências, de forma que 5% dos usuários do pool estão em conferências simultâneas. Por exemplo, em um pool de servidores Front-End doze e 80.000 usuários, enquanto a conferência de 250 usuários está acontecendo, Skype para Business Server suporta 3.750 outros usuários que participam de conferências menores.

Independentemente do número de usuários de hospedados no pool de Front-End ou servidor Standard Edition, Skype para Business Server suporta um mínimo de 125 outros usuários que participam de conferências menores no mesmo pool ou servidor que está hospedando a uma conferência de 250 usuários.

Para habilitar conferências que tenham entre 250 e 1.000 usuários, você pode configurar um pool de Front-End separado apenas para hospedar dessas conferências. Este pool de Front-End não hospeda nenhum usuário. Para obter detalhes, consulte [Planejar para grandes reuniões em Skype para Business Server](../../plan-your-deployment/conferencing/large-meetings.md).

Se sua organização tem muito mais conferências de modo misto vez pressupõe-se no modelo de usuário, você talvez seja necessário implantar mais servidores Front-End que podemos recomendação neste documento (até um máximo de 12 servidores Front-End). Para obter detalhes sobre as suposições no modelo de usuário, consulte [modelos de usuário Skype para Business Server](user-models.md).

## <a name="edge-server"></a>Servidor de Borda

> [!NOTE]
> Pools alongados não são suportados pela função desse servidor.

Você deve implantar um servidor de borda para cada 12.000 usuários remotos que irão acessar um site simultaneamente. No mínimo, recomendamos dois servidores de borda para alta disponibilidade. Estas recomendações consideram que o hardware para os servidores de borda cumpre as recomendações em [Server Hardware Platforms](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

Ao contar o número de usuários para os servidores de borda, inclua os usuários hospedados em aparelhos de filial persistente e servidores de filial persistente em filiais que estão associados um pool de Front-End neste site.

> [!NOTE]
> Para melhorar o desempenho do serviço de borda de webconferência V nos servidores de borda, / você deve habilitar o recebimento do lado do dimensionamento (RSS) nos adaptadores de rede em seus servidores de borda. O RSS permite que pacotes de entrada sejam tratados paralelamente por vários processadores no servidor. Para obter detalhes, verifique "[Receber lado dimensionamento (RSS) no Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731)". Para obter detalhes sobre como ativar RSS, consulte a documentação do seu adaptador de rede.

## <a name="director"></a>Diretor

> [!NOTE]
> Pools alongados não são suportados pela função desse servidor.

Se você implantar a função de servidor de diretor, recomendamos que você implante um diretor para cada 12.000 usuários remotos, que irão acessar um site simultaneamente. No mínimo, recomendamos dois Directors para alta disponibilidade. Estas recomendações consideram que o hardware para os servidores de borda cumpre as recomendações em [Server Hardware Platforms](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

Ao contar o número de usuários para os diretores, inclua os usuários hospedados em aparelhos de filial persistente e servidores de filial persistente em filiais que estão associados um pool de Front-End neste site.

## <a name="mediation-server"></a>Servidor de Mediação

> [!NOTE]
> Pools alongados não são suportados pela função desse servidor.

Se você colocar o servidor de mediação com o servidor Front-End, servidor de mediação é executado em cada servidor Front-End no pool e deverá fornecer capacidade suficiente para os usuários no pool.

Se você implantar um pool do servidor de mediação autônomo e, em seguida, quantos servidores de mediação implantar depende de vários fatores, incluindo o hardware usado para o servidor de mediação, o número de usuários de VoIP, você tem, o número de gateway peers que cada pool do servidor de mediação controles, o tráfego do horário de pico por meio desses gateways e a porcentagem de chamadas com mídia que ignora o servidor de mediação.

As tabelas a seguir fornecem uma diretriz para quantas chamadas simultâneas um servidor de mediação podem manipular, supondo que o hardware para os servidores de mediação atende aos requisitos em [Server Hardware Platforms](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx) e hyperthreading está habilitado. Para obter detalhes sobre escalabilidade do servidor de mediação, consulte [Estimating uso de voz e o tráfego para Skype para Business Server](estimating-voice-traffic.md) e [diretrizes de implantação para o servidor de mediação em Skype para Business Server](mediation-server-deployment-guidelines.md).

Todas as tabelas a seguir supõem a utilização resumida em [modelos de usuário Skype para Business Server](user-models.md).

**Capacidade do servidor de mediação autônoma: 70% de usuários internos, 30% de usuários externos com não ignorar a capacidade de chamadas (transcodificação de mídia executada pelo servidor de mediação)**

|**Hardware de servidor**|**Número máximo de chamadas**|**Número máximo de linhas T1**|**Número máximo de linhas E1**|
|:-----|:-----|:-----|:-----|
|Processador duplo, hex-core, CPU de 2,26 GHz hyper-threaded, **com hyper-threading desabilitado**, com 32 GB de memória e uma placa de adaptador de rede dual-port.  <br/> |1100  <br/> |46  <br/> |35  <br/> |
|Processador duplo, hex-core, CPU de 2,26 GHz hyper-threaded, com 32 GB de memória e uma placa de adaptador de rede dual-port.  <br/> |1500  <br/> |63  <br/> |47  <br/> |

> [!NOTE]
> Embora os servidores com 32 GB de memória foram usados para testes de desempenho, servidores com 16 GB de memória são suportados para o servidor de mediação autônomo e são suficientes para fornecer o desempenho mostrado nesta tabela.

**Capacidade do servidor de mediação (servidor de mediação colocado com o servidor Front-End) 70% de usuários internos, 30% de usuários externos, capacidade de chamada não ignorar (processamento de mídia executada pelo servidor de mediação)**

|**Hardware de servidor**|**Número máximo de chamadas**|
|:-----|:-----|
|Processador duplo, hex-core, CPU de 2,26 GHz hyper-threaded com hyper-threading e 2 placas de adaptador de rede de 1GB.  <br/> |150  <br/> |

> [!NOTE]
> Esse número é muito menor do que os números para o servidor de mediação autônomo. Isso acontece porque o servidor Front-End tem que lidar com outros recursos e funções para os 6600 usuários hospedagem nele, além de transcodificação necessária para chamadas de voz.

> [!NOTE]
> Para melhorar o desempenho do servidor de mediação, você deve habilitar o recebimento do lado do dimensionamento (RSS) nos adaptadores de rede em seus servidores de mediação. O RSS permite que pacotes de entrada sejam tratados paralelamente por vários processadores no servidor. Para obter detalhes, consulte "[Receive-Side Scaling no Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731)". Para obter detalhes sobre como ativar RSS, consulte a documentação do seu adaptador de rede.

## <a name="back-end-server"></a>Servidor Back-End

Embora grande parte das informações do banco de dados é armazenado principalmente em servidores Front-End, verifique se os que seus servidores Back-End acordo com as recomendações de hardware mencionadas anteriormente nesta seção e em [Server Hardware Platforms](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

Para fornecer alta disponibilidade do seu servidor Back-End, é recomendável implantar grupos de disponibilidade do AlwaysOn ou espelhamento de servidor. Para obter mais informações, consulte [alta disponibilidade do servidor Back-End no Skype para Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

## <a name="monitoring-and-archiving"></a>Monitoramento e Arquivamento

Se você implantar o monitoramento ou arquivamento, a funcionalidade de front-end desses serviços é executado nos servidores Front-End, monitoramento e arquivamento usam seu próprio armazenamento de banco de dados, separado do armazenamento de Back-End. Como alternativa, se você tiver implantado do Exchange 2013, você pode armazenar dados de arquivamento de mensagens instantâneas no Exchange, em vez de em um repositório SQL dedicado.

A tabela a seguir indica aproximadamente quanto armazenamento de banco de dados é exigido por usuário, por dia, para os dados de monitoramento e arquivamento.

||**CDR (Monitoramento)** <br/> |**QoE (Monitoramento)** <br/> |**Archiving** <br/> |
|:-----|:-----|:-----|:-----|
|Espaço em disco exigido por usuário, por dia  <br/> |49 KB  <br/> |28 KB  <br/> |57 KB  <br/> |

A Microsoft usou o hardware na tabela a seguir para p servidor de banco de dados para monitoramento e arquivamento durante seus testes de desempenho. O teste coletados os dados dos dois pools de Front-End, cada um deles contido 80.000 usuários.

**Hardware usado nos testes de desempenho de monitoramento e arquivamento**

|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Processador duplo de 64 bits, núcleo hexagonal, 2.26 gigahertz (GHz) ou superior  <br/> |
|Memória  <br/> |48 gigabytes (GB)  <br/> |
|Disco  <br/> |25 10.000-RPM discos rígidos com 300 GB em cada disco, com a configuração na tabela a seguir  <br/> |
|Rede  <br/> | 1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 recomendados, que exige agrupamento com um único endereço MAC e um único endereço IP)  <br/> |

**Configurações recomendadas de disco**

|**Unidade** <br/> |**Configuração RAID** <br/> |**Número de discos** <br/> |
|:-----|:-----|:-----|
|CDR, QoE e arquivos de banco de dados de arquivamento, em uma única unidade  <br/> |1+0  <br/> |16  <br/> |
|Arquivo de log do banco de dados de CDR  <br/> |1  <br/> |2  <br/> |
|Arquivo de log do banco de dados de QoE  <br/> |1  <br/> |2  <br/> |
|Arquivo de log do banco de dados de arquivamento  <br/> |1  <br/> |2  <br/> |

## <a name="video-interop-server-capacity"></a>Capacidade do servidor de interoperabilidade de vídeo

Se você implantar o servidor de interoperabilidade de vídeo e você precisa determinar a capacidade, examine o número máximo de sistemas de teleconferência de vídeo (VTCs) que farão parte chamadas simultâneas. Por exemplo, se você tiver 250 VTCs em sua organização e o seu modelo de usuário estima que no máximo, 20% delas podem estar em chamadas simultâneas, você baseará seu planejamento de capacidade em 50 VTCs simultâneas.


