---
title: Planejamento de capacidade para o Skype for Business Server 2019
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
description: Os tópicos desta seção ajudam a entender como planejar e implantar o Skype for Business Server para que você possa planejar adequadamente o número de usuários em sua organização e planejar a carga de servidor que suas atividades geram.
ms.openlocfilehash: 15f59d2052a4d73f6e1b1c09b10525b503958fea
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824025"
---
# <a name="capacity-planning-for-skype-for-business-server-2019"></a>Planejamento de capacidade para o Skype for Business Server 2019

Este artigo fornece orientação sobre quantos servidores você precisa em um site para o número de usuários nesse site, de acordo com o uso descrito em Modelos de usuário no [Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md)

## <a name="tested-hardware-platform"></a>Plataforma de hardware testada

Fizemos nossos testes de desempenho no hardware descrito na tabela a seguir. Todas as nossas recomendações e resultados são baseados nesse hardware. Se você decidir usar hardware menos poderoso do que o que vê listado aqui, lembre-se de que você pode enfrentar problemas de funcionalidade ou baixo desempenho.

**Hardware usado no teste de desempenho**

|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Processador duplo Intel Xeon E5-2673 v3, 6 núcleos, 2,4 gigahertz (GHz) ou superior.  <br/> Processadores Intel Itanium não são suportados para funções do Skype for Business Server 2019.  <br/> |
|Memória  <br/> |32 gigabytes (GB).  <br/> |
|Disco  <br/> |UMA DAS:  <br/> • 8 ou mais unidades de disco rígido de 10000 RPM com pelo menos 72 GB de espaço livre (dois dos discos usando RAID 1 e 6 usando RAID 10).  <br/> OU  <br/> • Unidades de estado sólido (SSDs) capazes de fornecer o mesmo espaço livre e desempenho semelhante a 8 unidades de disco mecânico de 10.000 RPM.  <br/> |
|Rede  <br/> |1 adaptador de rede de porta dupla, 1 Gbps ou superior (dois adaptadores de rede podem ser usados, mas eles precisam ser em equipe com um único endereço MAC e um único endereço IP).  <br/> As configurações dual ou  multi-homed não são suportadas para servidores front-end, servidores back-end e servidores Standard Edition. <br/> Desde que eles não sejam expostos ao sistema operacional e sejam usados para monitorar e gerenciar o hardware do servidor, você pode ter sistemas de gerenciamento fora de banda, como DRAC ou ILO. Este cenário não constitui um servidor multi-homed e é suportado.  <br/> |

## <a name="summary-of-results"></a>Resumo dos resultados

A tabela a seguir resume nossas recomendações.

|**Função de servidor**|**Número máximo de usuários suportados**|
|:-----|:-----|
|Pool de #A0 com dezesseis Servidores #A0 e Servidor #A0 ou um par de Servidores #A0 com SQL Always On para alta disponibilidade.  <br/> |106.000 usuários exclusivos conectados simultaneamente, além de 50% de vários pontos de presença (MPOP) representando instâncias não móveis, além de 40% dos usuários habilitados para Mobilidade para um total de 210.000 pontos de extremidade.  <br/> |
|Conferência A/V  <br/> |O serviço de Conferência A/V fornecido por um pool de Front-End suporta as conferências do pool, assumindo um tamanho máximo de conferência de 250 usuários e apenas uma conferência grande em execução por vez.  <br/> **Observação:** Além disso, você pode dar suporte a grandes conferências de 250 a 1.000 usuários implantando um pool de Front End separado com dois Servidores front-end para hospedar grandes conferências. Para obter detalhes, [consulte Planejar grandes reuniões no Skype for Business Server.](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md) <br/> |
|Um Servidor de Borda  <br/> |18.000 usuários remotos simultâneos.  <br/> |
|Um Diretor  <br/> |18.000 usuários remotos simultâneos.  <br/> |
|Monitoramento e arquivamento  <br/> |Os serviços front-end de Monitoramento e Arquivamento são executados em cada Servidor Front-End, em vez de em funções de servidor separadas.  <br/> O monitoramento e arquivamento ainda exigem seus próprios armazenamentos de banco de dados. Se você também executar o Exchange 2013 ou posterior, poderá manter seus dados de Arquivamento no Exchange, em vez de em um banco de dados SQL dedicado.  <br/> |
|Um Servidor de Mediação  <br/> |O Servidor de Mediação alocado com o Servidor front-end é executado em cada Servidor Front-End em um pool e deve fornecer capacidade suficiente para os usuários no pool. Para o Servidor de Mediação autônomo, consulte a seção "Servidor de Mediação" posteriormente neste tópico.  <br/> |
|Um servidor Standard Edition  <br/> |Recomendamos que, se você usar servidores Standard Edition para hospedar usuários, sempre use dois servidores, emparelhados usando as recomendações em Planejamento para Alta Disponibilidade e Recuperação [de Desastres.](https://technet.microsoft.com/library/15a72073-0336-45dd-b2a0-35e7522c6000.aspx) Cada servidor no par pode hospedar até 2.500 usuários e, se um servidor falhar, o servidor restante poderá suportar 5.000 usuários em um cenário de failover.  <br/>  Se sua implantação incluir uma quantidade significativa de tráfego de áudio ou vídeo, o desempenho do servidor poderá ser prejudicado com mais de 2.500 usuários por servidor. Nesse caso, você deve considerar a adição de mais servidores Standard Edition ou a mudança para o Skype for Business Server Enterprise Edition. <br/> |

## <a name="front-end-server"></a>Servidor Front-End

> [!NOTE]
> Pools estendidos não são suportados para esta função de servidor.

Em um pool de #A0, você deve ter um Servidor #A0 para cada 6.660 usuários em seu pool, supondo que o hyper-threading está habilitado em todos os servidores no pool, que você está usando o SQL Server Express Edition e que o hardware do servidor atende às recomendações nos requisitos de servidor para [o Skype for Business Server 2019.](system-requirements.md) O número máximo de usuários em um pool de #A0 é 106.000, novamente supondo que o hyper-threading está habilitado e que o SQL Server Express Edition seja usado em todos os servidores em seu pool. Se você tiver mais de 106.000 usuários em um site, poderá implantar mais de um pool de Front-End.

Quando você contabilizou o número de usuários em um pool de Front-End, inclua todos os usuários que estão em Aparelhos de Filial E Servidores de FilialVivíveis em filiais associadas a esse pool de Front-End.

Quando um servidor ativo fica indisponível, suas conexões são transferidas automaticamente para os outros servidores no pool. Em um cenário em que você tem 30.000 usuários e cinco Servidores Front-End, se um servidor não estiver disponível, as conexões de 6000 de seus usuários precisarão ser transferidas para os outros quatro servidores restantes. Esses quatro servidores restantes terão, cada um, 7500 usuários, o que é um número maior do que o recomendado.

Se, em vez disso, você tiver iniciado com seis Servidores front-end para seus 30.000 usuários e um ficar indisponível, um total de 5.000 usuários precisará se mover para os cinco servidores restantes. Esses cinco servidores restantes hospedarão 6.000 usuários, que está no intervalo recomendado.

O número máximo de usuários em um pool de Front-End é 106.000. O número máximo de Servidores front-end em um pool é 16.

Para um pool de front-end com 80.000 usuários, 16 Servidores front-end serão bons para o desempenho, em implantações típicas que seguem os modelos de usuário no [Skype for Business Server.](../../SfbServer/plan-your-deployment/capacity/user-models.md) As implantações projetadas para dar suporte a failover de recuperação de desastres pressupom que um máximo de 53.000 usuários podem ser hospedados em cada um dos dois pools de Front End emparelhados, nos quais cada pool tem Servidores Front End suficientes para conter os usuários em ambos os pools, caso seja necessário fazer failover de um pool para o outro.

O número de usuários suportados com bom desempenho por um determinado pool de Front-End pode ser diferente desses números pelos seguintes motivos:

- O hardware dos servidores front-end não está de acordo com as recomendações.
- Em vez de usar o SQL Server Express Edition, você usa outro SQL Server Edition, pode ser capaz de hospedar usuários adicionais em cada pool de Front-End.
- O uso da sua organização é muito diferente dos modelos de usuário, por exemplo, se você tiver muito mais tráfego de conferência.

A tabela a seguir mostra a largura de banda média para IM e presença, dado o modelo de usuário, conforme definido nos modelos de [usuário no Skype for Business Server.](../../SfbServer/plan-your-deployment/capacity/user-models.md)

|**Largura de banda média por usuário**|**Requisitos de largura de banda por Servidor Front End com 6.660 usuários**|
|:-----|:-----|
|3 a 3,75 KBps  <br/> |13 MBps  <br/> |

> [!NOTE]
> Para melhorar o desempenho de mídia da funcionalidade de Servidor de Mediação e Conferência A/V co-localizada em seus Servidores Front-End, você deve habilitar o RSS (receive-side scaling) nos adaptadores de rede em seus Servidores Front-End. O RSS permite que pacotes recebidos sejam manipulados em paralelo por vários processadores no servidor. Para obter detalhes, [consulte Receive Side Scaling (RSS) na documentação do Windows Server 2012.](https://go.microsoft.com/fwlink/p/?LinkId=620365) Para obter detalhes sobre como habilitar o RSS, você precisará consultar a documentação do adaptador de rede.

## <a name="conferencing-maximums"></a>Máximos de Conferência

Dado o modelo de usuário de que 5% dos usuários em um pool podem estar em uma conferência a qualquer momento, um pool de 106.000 usuários poderia ter cerca de 5.300 usuários em conferências simultaneamente. Espera-se que essas conferências sejam uma mistura de mídias (algumas somente IM, algumas IM com áudio, algumas áudio/vídeo, por exemplo) e de número de participantes. Não há um limite rígido para o número real de conferências permitidas e o uso real determina o desempenho real. Por exemplo, se sua organização tem muito mais conferências de modo misto do que as que são presumidas no modelo de usuário, talvez seja necessário implantar mais Servidores Front End ou Servidores de Conferência A/V do que as recomendações encontradas neste artigo. Para obter detalhes sobre as suposições no modelo de usuário, consulte [Modelos de usuário no Skype for Business Server.](../../SfbServer/plan-your-deployment/capacity/user-models.md)

O tamanho máximo de conferência com suporte hospedado por um pool de front-end regular do Skype for Business Server que também hospeda usuários é de 250 participantes. Enquanto uma conferência de 250 usuários está acontecendo, o pool ainda oferece suporte a outras conferências, de tal forma que um total de 5% dos usuários do pool estão em conferências simultâneas. Por exemplo, em um pool de 16 Servidores front-end e 106.000 usuários, enquanto a conferência de 250 usuários está acontecendo, o Skype for Business Server suporta 5.050 outros usuários participando de conferências menores.

Independentemente do número de usuários hospedadas no pool de front-end ou servidor Standard Edition, o Skype for Business Server suporta um mínimo de 125 outros usuários participando de conferências menores no mesmo pool ou servidor que está hospedando uma conferência de 250 usuários.

Para habilitar conferências com entre 250 e 1.000 usuários, você pode configurar um pool de Front-End separado apenas para hospedar essas conferências. Esse pool de Front-End não hospedará nenhum usuário. Para obter detalhes, consulte [Planejar grandes reuniões no Skype for Business Server.](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md)

Se a sua organização tem muito mais conferências de modo misto do que são presumidas no modelo de usuário, talvez seja necessário implantar mais Servidores Front End do que recomendamos neste documento (até um limite de 16 Servidores Front-End). Para obter detalhes sobre as suposições no modelo de usuário, consulte [Modelos de usuário no Skype for Business Server.](../../SfbServer/plan-your-deployment/capacity/user-models.md)

## <a name="edge-server"></a>Servidor de Borda

> [!NOTE]
> Pools estendidos não são suportados para esta função de servidor.

Você deve implantar um Servidor de Borda para cada 18.000 usuários remotos que acessarão um site simultaneamente. São recomendados no mínimo dois Servidores de Borda para alta disponibilidade. Essas recomendações presumem que o hardware para seus Servidores de Borda atenda às recomendações em [Plataformas de Hardware de Servidor.](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)

Ao contar o número de usuários para os Servidores de Borda, inclua os usuários hospedados em Aparelhos de Filial Persistente e Servidores de Filial Persistente em filiais associadas a um pool de Front End pool neste local.

> [!NOTE]
> Para aprimorar o desempenho do serviço de Borda de Conferência A/V em seus Servidores de Borda, você deve habilitar o receive-side scaling (RSS) nos adaptadores de rede em seus Servidores de Borda. O RSS permite que pacotes recebidos sejam manipulados em paralelo por vários processadores no servidor. Para obter detalhes, [consulte Receive Side Scaling (RSS) no Windows Server 2012.](https://go.microsoft.com/fwlink/p/?linkId=268731) Para obter detalhes sobre como habilitar o RSS, você precisará consultar a documentação do adaptador de rede.

## <a name="director"></a>Diretor

> [!NOTE]
> Pools estendidos não são suportados para esta função de servidor.

Se você implantar a função de servidor Diretor, recomendamos implantar um Diretor para cada 18.000 usuários remotos que acessarão um site simultaneamente. São recomendados no mínimo dois Diretores para alta disponibilidade. Essas recomendações presumem que o hardware para seus Servidores de Borda atenda às recomendações em [Plataformas de Hardware de Servidor.](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)

Ao contar o número de usuários para os Diretores, inclua os usuários hospedados em Aparelhos de Filial Persistente e Servidores de Filial Persistente em filiais associadas a um pool de Front End pool neste local.

## <a name="mediation-server"></a>Servidor de Mediação

> [!NOTE]
> Pools estendidos não são suportados para esta função de servidor.

Se você cola o Servidor de Mediação com o Servidor Front-End, o Servidor de Mediação é executado em cada Servidor Front-End no pool e deve fornecer capacidade suficiente para os usuários no pool.

Se você implantar um pool de Servidor de Mediação autônomo, quantos Servidores de Mediação implantar dependerão de vários fatores, incluindo o hardware usado para o Servidor de Mediação, o número de usuários VoIP que você tem, o número de pares de gateway que cada pool do Servidor de Mediação controla, o tráfego de horário ocupado por esses gateways e a porcentagem de chamadas com mídia que ignora o Servidor de Mediação.

As tabelas a seguir fornecem uma diretriz para quantas chamadas simultâneas um Servidor de Mediação pode lidar, supondo que o hardware para os Servidores de Mediação atenda aos requisitos nas [Plataformas](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx) de Hardware do Servidor e que o hyper-threading está habilitado. Para obter detalhes sobre a escalabilidade do Servidor de Mediação, consulte [Estimating voice usage and traffic for Skype for Business Server and](../../SfbServer/plan-your-deployment/capacity/estimating-voice-traffic.md) Deployment [guidelines for Mediation Server in Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/mediation-server-deployment-guidelines.md).

Todas as tabelas a seguir presumem o uso como resumido [nos modelos de usuário no Skype for Business Server.](../../SfbServer/plan-your-deployment/capacity/user-models.md)

**Capacidade do Servidor de Mediação Autônomo: 70% de Usuários Internos, 30% de usuários externos com capacidade de chamada não ignorada (transcodificação de mídia executada pelo Servidor de Mediação)**

|**Hardware de servidor**|**Número máximo de chamadas**|**Número máximo de linhas T1**|**Número máximo de linhas E1**|
|:-----|:-----|:-----|:-----|
|Intel Xeon E5-2673 v3 dual processor, 6-core, 2.4 gigahertz (GHz) ou superior com **hyper-threading desabilitado,** com 64 GB de memória e uma placa de adaptador de rede de porta dupla.  <br/> |1500  <br/> |64  <br/> |49  <br/> |
|Intel Xeon E5-2673 v3 dual processor, 6-core, 2.4 gigahertz (GHz) ou superior, com 64 GB de memória e uma placa de adaptador de rede de porta dupla.  <br/> |2000  <br/> |88  <br/> |66  <br/> |

> [!NOTE]
> Embora servidores com 64 GB de memória tenham sido usados para testes de desempenho, servidores com 32 GB de memória são suportados para o Servidor de Mediação autônomo e são suficientes para fornecer o desempenho mostrado nesta tabela.

**Capacidade do Servidor de Mediação (Servidor de Mediação alocado com Servidor Front-End) 70% de usuários internos, 30% de usuários externos, capacidade de chamada não ignorada (processamento de mídia executado pelo Servidor de Mediação)**

|**Hardware de servidor**|**Número máximo de chamadas**|
|:-----|:-----|
|Intel Xeon E5-2673 v3 processador duplo, 6 núcleos, 2.4 gigahertz (GHz) ou superior., com 64 GB de memória e 2 placas de adaptador de rede de 1 GB.  <br/> |200  <br/> |

> [!NOTE]
> Esse número é muito menor do que os números do Servidor de Mediação autônomo. Isso porque o Servidor front-end precisa lidar com outros recursos e funções para os 6.600 usuários que o estão utilizando, além da transcodificação necessária para chamadas de voz.

> [!NOTE]
> Para melhorar o desempenho do Servidor de Mediação, você deve habilitar o RSS (receive-side scaling) nos adaptadores de rede em seus Servidores de Mediação. O RSS permite que pacotes recebidos sejam manipulados em paralelo por vários processadores no servidor. Para obter detalhes, consulte "[Receive-Side Scaling in Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731)". Para obter detalhes sobre como habilitar o RSS, você precisará consultar a documentação do adaptador de rede.

## <a name="back-end-server"></a>Servidor de Back-End

Embora grande parte das informações do banco de dados seja armazenada principalmente nos Servidores Front-End, você deve garantir que seus Servidores Back-End atendem às recomendações de hardware listadas anteriormente nesta seção e em Plataformas de Hardware de [Servidor.](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)

Para fornecer alta disponibilidade do servidor back-end, recomendamos implantar Grupos de Disponibilidade AlwaysOn ou espelhamento de servidor. Para obter mais informações, consulte [Back End Server high availability in Skype for Business Server](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

## <a name="monitoring-and-archiving"></a>Monitoramento e arquivamento

Se você implantar Monitoramento ou Arquivamento, a funcionalidade de front-end desses serviços será executado nos Servidores Front-End, monitoramento e arquivamento, cada um utilizando seu próprio armazenamento de banco de dados, separado do armazenamento back-end. Como alternativa, se você tiver o Exchange 2013 implantado, poderá armazenar dados de arquivamento de mensagens instantâneas no Exchange em vez de em um armazenamento SQL dedicado.

A tabela a seguir indica aproximadamente quanto armazenamento de banco de dados é necessário por usuário por dia para os dados de Monitoramento e Arquivamento.

||**CDR (Monitoramento)** <br/> |**QoE (Monitoramento)** <br/> |**Arquivamento** <br/> |
|:-----|:-----|:-----|:-----|
|Espaço em disco necessário por usuário por dia  <br/> |49 KB  <br/> |28 KB  <br/> |57 KB  <br/> |

A Microsoft usou o hardware na tabela a seguir para o servidor de banco de dados para monitoramento e arquivamento durante seus testes de desempenho. O teste coletou os dados de dois pools de Front-End, cada um com 80.000 usuários.

**Hardware usado no monitoramento e no teste de desempenho de arquivamento**

|**Componente de hardware**|**Recomendado**|
|:-----|:-----|
|CPU  <br/> |Processador duplo Intel Xeon E5-2673 v3, 6 núcleos, 2,4 gigahertz (GHz) ou superior.  <br/> |
|Memória  <br/> |48 GB  <br/> |
|Disco  <br/> | UMA DAS:<br/> • 4 ou mais unidades de disco rígido de 10000 RPM com pelo menos 72 GB de espaço livre em disco (os discos devem estar em uma configuração raid 1 de 2x). <br/>OU <br/>• Unidades de estado sólido (SSDs) capazes de fornecer o mesmo espaço livre e desempenho semelhante a 4 unidades de disco mecânico de 10.000 RPM.   <br/> |
|Rede  <br/> | 1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 recomendados, o que requer um único endereço MAC e um único endereço IP).  <br/> |

**Configurações de disco recomendadas**

|**Drive** <br/> |**Configuração RAID** <br/> |**Número de discos** <br/> |
|:-----|:-----|:-----|
|Arquivos de dados de banco de dados de CDR, QoE e Arquivamento, em uma única unidade  <br/> |1+0  <br/> |16   <br/> |
|Arquivo de log do banco de dados CDR  <br/> |1   <br/> |2   <br/> |
|Arquivo de log do banco de dados QoE  <br/> |1   <br/> |2   <br/> |
|Arquivo de log do banco de dados de arquivamento  <br/> |1   <br/> |2   <br/> |

## <a name="video-interop-server-capacity"></a>Capacidade do Servidor de Interop de Vídeo

Se você implantar o Servidor de Interop de Vídeo e precisar determinar a capacidade, você verificará o número máximo de Sistemas de Teleconferência de Vídeo (VTCs) que estarão em chamadas simultâneas. Por exemplo, se você tiver 250 VTCs em sua organização e seu modelo de usuário estima que, no máximo, 20% delas podem estar em chamadas simultâneas, você baseia seu planejamento de capacidade em 50 VTCs simultâneas.

