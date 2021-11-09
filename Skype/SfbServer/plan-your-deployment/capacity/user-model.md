---
title: Uso do modelo de usuário de planejamento de capacidade para Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
description: Este artigo fornece orientações sobre quantos servidores você precisa em um site para o número de usuários nesse site, de acordo com o uso descrito em Modelos de usuário em Skype for Business Server.
ms.openlocfilehash: 145e790c0f6c7ceeaa7330c0cd48ad68bc15b331
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846354"
---
# <a name="capacity-planning-user-model-usage-for-skype-for-business-server"></a>Uso do modelo de usuário de planejamento de capacidade para Skype for Business Server

Este artigo fornece orientações sobre quantos servidores você precisa em um site para o número de usuários nesse site, de acordo com o uso descrito em Modelos de usuário [em Skype for Business Server](user-models.md).

> [!NOTE]
> Todas as recomendações neste artigo pressuem que você tenha instalado Skype for Business Atualização Cumulativa, novembro de 2015 ou posterior em seus servidores.

## <a name="tested-hardware-platform"></a>Plataforma de hardware testada

Fizemos nosso teste de desempenho no hardware descrito na tabela abaixo. Todas as nossas recomendações e resultados são baseados nesse hardware. Se você decidir tentar usar hardware menos poderoso do que o que você vê listado aqui, lembre-se de que você pode enfrentar problemas de funcionalidade ou desempenho ruim. Essas recomendações de hardware são as mesmas do Lync Server 2013, se isso for útil (e em cenários de atualização, pode ser).

**Hardware usado no teste de desempenho**

|Componente de hardware|Recomendado|
|:-----|:-----|
|CPU   |Processador duplo de 64 bits, hex-core, 2,26 gigahertz (GHz) ou superior.  <br/> Os processadores Intel Itanium não têm suporte para funções Skype for Business Server servidor.   |
|Memória   |32 gigabytes (GB).   |
|Disco   |8 ou mais unidades de disco rígido de 10.000 RPM com pelo menos 72 GB de espaço livre em disco. Dois dos discos devem usar RAID 1 e seis devem usar RAID 10.  <br/> - OU - <br/>Unidades de estado sólido (SSDs) que fornecem desempenho semelhante a 8 unidades de disco mecânicas de 10.000 RPM.  |
|Rede   |1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 recomendado, o que requer uma equipe com um único endereço MAC e um único endereço IP).   |

## <a name="summary-of-results"></a>Resumo dos resultados

A tabela a seguir resume nossas recomendações.

|Função de servidor|Número máximo de usuários suportados|
|:-----|:-----|
|Pool de Front-End com doze Servidores Front-End e um Servidor Back-End ou um par espelhado de Servidores Back-End.   |80.000 usuários exclusivos conectados simultaneamente, mais 50% de vários pontos de presença (MPOP) que representam instâncias não móveis, além de 40% dos usuários habilitados para Mobilidade para um total de 152.000 pontos de extremidade.   |
|Conferência A/V   |O serviço de Conferência A/V fornecido por um pool de Front-End dá suporte às conferências do pool supondo um tamanho máximo de conferência de 250 usuários e apenas uma conferência tão grande em execução por vez.  <br/> **Observação:** Além disso, você pode dar suporte a grandes conferências entre 250 e 1000 usuários implantando um pool de Front-End separado com dois Servidores Front-End para hospedar as grandes conferências. Para obter detalhes, [consulte Plan for large meetings in Skype for Business Server](../../plan-your-deployment/conferencing/large-meetings.md).   |
|Um Servidor de Borda   |12.000 usuários remotos simultâneos.   |
|Um Diretor   |12.000 usuários remotos simultâneos.   |
|Monitoramento e arquivamento   |Os serviços front-end de Monitoramento e Arquivamento são executados em cada Servidor Front-End, em vez de em funções de servidor separadas.  <br/> O monitoramento e o arquivamento ainda exigem seus próprios armazenamentos de banco de dados. Se você também executar o Exchange 2013 ou posterior, poderá manter seus dados de arquivamento em Exchange, em vez de em um banco de dados SQL dedicado.   |
|Um Servidor de Mediação   |O Servidor de Mediação alocado com o Servidor Front-End é executado em todos os Servidores Front-End em um pool e deve fornecer capacidade suficiente para os usuários no pool. Para o Servidor de Mediação autônomo, consulte a seção "Servidor de Mediação" posteriormente neste tópico.   |
|Um servidor Standard Edition   |Recomendamos que, se você usar servidores Edição Standard para hospedar usuários, sempre use dois servidores, emparelhados usando as recomendações em Planejamento para Alta Disponibilidade e Recuperação [de Desastres.](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-high-availability-and-disaster-recovery) Cada servidor no par pode hospedar até 2.500 usuários e, se um servidor falhar, o servidor restante poderá suportar 5.000 usuários em um cenário de failover.  <br/>  Se sua implantação incluir uma quantidade significativa de tráfego de áudio ou vídeo, o desempenho do servidor poderá sofrer com mais de 2.500 usuários por servidor. Nesse caso, você deve considerar adicionar mais servidores Edição Standard ou mover para Skype for Business Server Edição Enterprise.  |

## <a name="front-end-server"></a>Servidor Front-End

> [!NOTE]
> Pools estendidos não são suportados para essa função de servidor.

Em um pool de Front-End, você deve ter um Servidor De Front-End para cada 6.660 usuários em seu pool, supondo que o hiper threading está habilitado em todos os servidores do pool e que o hardware do servidor atende às recomendações nos requisitos do servidor para o [Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md) ou requisitos do [sistema para Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md). O número máximo de usuários em um pool de Front-End é de 80.000, novamente supondo que o hiper threading está habilitado em todos os servidores em seu pool. Se houver mais de 80.000 usuários em um site, é possível implantar mais de um pool de Front End.

Quando você conta para o número de usuários em um pool de Front-End, inclui todos os usuários que estão em casa em Aparelhos de Filial E Servidores de Filial Desaviváveis em filiais associadas a esse pool de Front-End.

Quando um servidor ativo fica indisponível, suas conexões são transferidas automaticamente para os outros servidores no pool. Em um cenário em que você tem 30.000 usuários e cinco Servidores Front-End, se um servidor não estiver disponível, as conexões de 6.000 de seus usuários precisarão ser transferidas para seus outros quatro servidores restantes. Esses quatro servidores restantes terão, em seguida, 7500 usuários, que é um número maior do que o recomendado.

Se, em vez disso, você tiver começado com seis Servidores Front-End para seus 30.000 usuários e um ficar indisponível, um total de 5.000 usuários precisará se mover para os cinco servidores restantes. Esses cinco servidores restantes então hospedarão 6.000 usuários, que está no intervalo recomendado.

O número máximo de usuários em um pool de Front End é 80.000. O número máximo de Servidores Front-End em um pool é 12.

Para um pool de Front-End com 80.000 usuários, doze Servidores Front-End serão bons para o desempenho, em implantações típicas que seguem os modelos de usuário em [Skype for Business Server](user-models.md). As implantações projetadas para dar suporte ao failover de recuperação de desastres pressupom que um máximo de 40.000 usuários podem ser hospedados em cada um dos dois pools front-end emparelhados, nos quais cada pool tem Servidores Front-End suficientes para conter os usuários em ambos os pools, caso um pool precise ser reprovado para o outro.

O número de usuários suportados com bom desempenho por um pool de Front-End específico pode ser diferente desses números pelos seguintes motivos:

- O hardware para seus Servidores Front-End não atendem às recomendações.

- O uso da sua organização é muito diferente dos modelos de usuário, por exemplo, se você tiver muito mais tráfego de conferência.

A tabela a seguir mostra a largura de banda média para IM e presença, dado o modelo de usuário, conforme definido em Modelos de [usuário em Skype for Business Server](user-models.md).

|Largura de banda média por usuário|Requisitos de largura de banda por Servidor Front-End com 6.660 usuários|
|:-----|:-----|
|1.3 Kpbs   |13 Mbps   |

> [!NOTE]
> Para melhorar o desempenho de mídia da funcionalidade do Servidor de Conferência e Mediação A/V em seus Servidores Front-End, você deve habilitar o RSS (dimensionamento do lado de recebimento) nos adaptadores de rede em seus Servidores Front-End. O RSS permite que pacotes recebidos sejam manipulados em paralelo por vários processadores no servidor. Para obter detalhes, [consulte Receive Side Scaling (RSS) na documentação Windows Server 2012 .](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11)) Para obter detalhes sobre como habilitar o RSS, você precisará consultar a documentação do adaptador de rede.

## <a name="conferencing-maximums"></a>Máximos de Conferência

Dado o modelo de usuário de que 5% dos usuários em um pool podem estar em uma conferência a qualquer momento, um pool de 80.000 usuários poderia ter cerca de 4.000 usuários em conferências simultaneamente. Espera-se que essas conferências sejam uma mistura de mídias (algumas somente IM, algumas IM com áudio, algumas áudio/vídeo, por exemplo) e de número de participantes. Não há um limite rígido para o número real de conferências permitidas e o uso real determina o desempenho real. Por exemplo, se sua organização tiver muito mais conferências de modo misto do que são assumidas no modelo de usuário, talvez seja necessário implantar mais Servidores Front-End ou Servidores de Conferência A/V do que as recomendações encontradas neste artigo. Para obter detalhes sobre as suposições no modelo de usuário, consulte [User models in Skype for Business Server](user-models.md).

O tamanho máximo de conferência com suporte hospedado por um pool Skype for Business Server front-end regular que também hospeda usuários é de 250 participantes. Enquanto uma conferência de 250 usuários está acontecendo, o pool ainda dá suporte a outras conferências, de forma que um total de 5% dos usuários do pool esteja em conferências simultâneas. Por exemplo, em um pool de doze Servidores Front-End e 80.000 usuários, enquanto a conferência de 250 usuários está acontecendo, o Skype for Business Server oferece suporte a 3.750 outros usuários que participam de conferências menores.

Independentemente do número de usuários no pool de Front-End ou no servidor Edição Standard, o Skype for Business Server oferece suporte a no mínimo 125 outros usuários que participam de conferências menores no mesmo pool ou servidor que está hospedando uma conferência de 250 usuários.

Para habilitar conferências que tenham entre 250 e 1.000 usuários, você pode configurar um pool de Front-End separado apenas para hospedar essas conferências. Esse pool de Front-End não hospedará nenhum usuário. Para obter detalhes, consulte [Plan for large meetings in Skype for Business Server](../../plan-your-deployment/conferencing/large-meetings.md).

Se sua organização tiver muito mais conferências de modo misto do que são presumidas no modelo de usuário, talvez seja necessário implantar mais Servidores Front-End do que recomendamos neste documento (até um limite de 12 Servidores Front-End). Para obter detalhes sobre as suposições no modelo de usuário, consulte [User models in Skype for Business Server](user-models.md).

## <a name="edge-server"></a>Servidor de Borda

> [!NOTE]
> Pools estendidos não são suportados para essa função de servidor.

Você deve implantar um Servidor de Borda para cada 12.000 usuários remotos que acessarão um site simultaneamente. São recomendados no mínimo dois Servidores de Borda para alta disponibilidade. Essas recomendações pressuem que o hardware para seus Servidores de Borda atende às recomendações em [Plataformas de Hardware do Servidor.](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)

Ao contar o número de usuários para os Servidores de Borda, inclua os usuários hospedados em Aparelhos de Filial Persistente e Servidores de Filial Persistente em filiais associadas a um pool de Front End pool neste local.

> [!NOTE]
> Para aprimorar o desempenho do serviço de Borda de Conferência A/V em seus Servidores de Borda, você deve habilitar o receive-side scaling (RSS) nos adaptadores de rede em seus Servidores de Borda. O RSS permite que pacotes recebidos sejam manipulados em paralelo por vários processadores no servidor. Para obter detalhes, verifique " Escala do[lado de recebimento (RSS) no Windows Server 2012](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11))". Para obter detalhes sobre como habilitar o RSS, você precisará consultar a documentação do adaptador de rede.

## <a name="director"></a>Diretor

> [!NOTE]
> Pools estendidos não são suportados para essa função de servidor.

Se você implantar a função de servidor Diretor, recomendamos implantar um Diretor para cada 12.000 usuários remotos que acessarão um site simultaneamente. São recomendados no mínimo dois Diretores para alta disponibilidade. Essas recomendações pressuem que o hardware para seus Servidores de Borda atende às recomendações em [Plataformas de Hardware do Servidor.](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)

Ao contar o número de usuários para os Diretores, inclua os usuários hospedados em Aparelhos de Filial Persistente e Servidores de Filial Persistente em filiais associadas a um pool de Front End pool neste local.

## <a name="mediation-server"></a>Servidor de Mediação

> [!NOTE]
> Pools estendidos não são suportados para essa função de servidor.

Se você colocar o Servidor de Mediação com o Servidor de Front-End, o Servidor de Mediação será executado em todos os Servidores Front-End do pool e deverá fornecer capacidade suficiente para os usuários no pool.

Se você implantar um pool de Servidor de Mediação autônomo, quantos Servidores de Mediação implantar dependerão de muitos fatores, incluindo o hardware usado para o Servidor de Mediação, o número de usuários VoIP que você tem, o número de pares de gateway que cada pool do Servidor de Mediação controla, o tráfego de horas de ocupado por esses gateways e a porcentagem de chamadas com mídia que ignora o Servidor de Mediação.

As tabelas a seguir fornecem uma diretriz para quantas chamadas simultâneas um Servidor de Mediação pode manipular, supondo que o hardware para os Servidores de Mediação atenda aos requisitos em [Plataformas](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms) de Hardware do Servidor e que o hiper threading está habilitado. Para obter detalhes sobre a escalabilidade do Servidor de Mediação, consulte [Estimando](estimating-voice-traffic.md) o uso e o tráfego de voz para Skype for Business Server e diretrizes de implantação para o Servidor de [Mediação em Skype for Business Server](mediation-server-deployment-guidelines.md).

Todas as tabelas a seguir pressuem o uso como resumido em [Modelos de usuário em Skype for Business Server](user-models.md).

**Capacidade do Servidor de Mediação Autônomo: 70% Usuários Internos, 30% Usuários externos com capacidade de chamada não ignorada (transcodificação de mídia executada pelo Servidor de Mediação)**

|Hardware de servidor|Número máximo de chamadas|Número máximo de linhas T1|Número máximo de linhas E1|
|:-----|:-----|:-----|:-----|
|Processador duplo, núcleo hexagonar, CPU hiper threaded de 2,26 GHz com hiper **threading** desabilitado , com memória de 32 GB e uma placa de adaptador de rede de porta dupla.   |1100   |46   |35   |
|Processador duplo, hex core, CPU hiper threaded de 2,26 GHz, com memória de 32 GB e uma placa adaptador de rede de porta dupla.   |1500   |63   |47   |

> [!NOTE]
> Embora servidores com 32 GB de memória tenham sido usados para testes de desempenho, servidores com 16 GB de memória são suportados para um Servidor de Mediação autônomo e são suficientes para fornecer o desempenho mostrado nesta tabela.

**Capacidade do servidor de mediação (Servidor de Mediação alocado com servidor front-end) 70% usuários internos, 30% usuários externos, capacidade de chamada não ignorada (Processamento de mídia executado pelo Servidor de Mediação)**

|Hardware de servidor|Número máximo de chamadas|
|:-----|:-----|
|Processador duplo, núcleo hexagonáx, CPU hiper threaded de 2,26 GHz, com memória de 32 GB e cartões adaptadores de rede de 2 1 GB.   |150   |

> [!NOTE]
> Esse número é muito menor do que os números do Servidor de Mediação autônomo. Isso porque o Servidor front-end precisa lidar com outros recursos e funções para os 6600 usuários que estão nele, além da transcodificação necessária para chamadas de voz.

> [!NOTE]
> Para melhorar o desempenho do Servidor de Mediação, você deve habilitar o RSS (dimensionamento do lado de recebimento) nos adaptadores de rede em seus Servidores de Mediação. O RSS permite que pacotes recebidos sejam manipulados em paralelo por vários processadores no servidor. Para obter detalhes, consulte "[Escala do lado](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11))do recebimento no Windows Server 2012 ". Para obter detalhes sobre como habilitar o RSS, você precisará consultar a documentação do adaptador de rede.

## <a name="back-end-server"></a>Servidor de Back-End

Embora grande parte das informações do banco de dados seja armazenada principalmente nos Servidores Front-End, você deve garantir que seus Servidores Back-End atendem às recomendações de hardware listadas anteriormente nesta seção e em Plataformas de [Hardware do Servidor.](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)

Para fornecer alta disponibilidade do servidor back-end, recomendamos a implantação de Grupos de Disponibilidade AlwaysOn ou espelhamento de servidor. Para obter mais informações, consulte [Back End Server high availability in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

## <a name="monitoring-and-archiving"></a>Monitoramento e arquivamento

Se você implantar o Monitoramento ou o Arquivamento, a funcionalidade de front-end desses serviços será executado nos Servidores front-end, monitoramento e arquivamento, cada um deles usa seu próprio armazenamento de banco de dados, separado do armazenamento de Back-End. Como alternativa, se você tiver Exchange 2013 implantado, poderá armazenar dados de arquivamento de mensagens instantâneas no Exchange em vez de em um armazenamento de SQL dedicado.

A tabela a seguir indica aproximadamente quanto armazenamento de banco de dados é necessário por usuário por dia para dados de Monitoramento e Arquivamento.

|&nbsp;|CDR (Monitoramento)  |QoE (Monitoramento)  |Arquivamento  |
|:-----|:-----|:-----|:-----|
|Espaço em disco exigido por usuário por dia   |49 KB   |28 KB   |57 KB   |

A Microsoft usou o hardware na tabela a seguir para o servidor de banco de dados para Monitoramento e Arquivamento durante seu teste de desempenho. Os testes coletaram os dados de dois pools de Front-End, cada um deles com 80.000 usuários.

**Hardware usado no teste de desempenho de monitoramento e arquivamento**

|Componente de hardware|Recomendado|
|:-----|:-----|
|CPU   |Processador duplo de 64 bits, núcleo hexagonal, 2.26 gigahertz (GHz) ou superior   |
|Memória   |48 gigabytes (GB)   |
|Disco   |25 unidades de disco rígido de 10.000 RPM com 300 GB em cada disco, com a configuração na tabela a seguir   |
|Rede   | 1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 recomendado, que exige agrupamento com um único endereço MAC e um único endereço IP)   |

**Configurações de disco recomendadas**

|Unidade  |Configuração RAID  |Número de discos  |
|:-----|:-----|:-----|
|Arquivos de dados de banco de dados de CDR, QoE e Arquivamento, em uma única unidade   |1+0   |16   |
|Arquivo de log do banco de dados CDR   |1   |2   |
|Arquivo de log do banco de dados QoE   |1   |2   |
|Arquivo de log de banco de dados de arquivamento   |1   |2   |

## <a name="video-interop-server-capacity"></a>Capacidade do Servidor de Interop de Vídeo

Se você implantar o Servidor de Interop de Vídeo e precisar determinar a capacidade, você olhará para o número máximo de VTCs (Sistemas de Teleconferência de Vídeo) que estarão em chamadas simultâneas. Por exemplo, se você tiver 250 VTCs em sua organização e seu modelo de usuário estima que, no máximo, 20% deles podem estar em chamadas simultâneas, você baseia seu planejamento de capacidade em 50 VTCs simultâneos.