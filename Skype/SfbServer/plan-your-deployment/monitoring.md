---
title: Plano para monitoramento no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
description: 'Resumo: Revise esse tópico durante o planejamento para o serviço de monitoramento no Skype de Business Server.'
ms.openlocfilehash: cfe5e0eb31ca2badb3c4610f33c0761a98972ce7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213911"
---
# <a name="plan-for-monitoring-in-skype-for-business-server"></a>Plano para monitoramento no Skype para Business Server

**Resumo:** Analise este tópico durante o planejamento para o serviço de monitoramento no Skype de Business Server.

O serviço de monitoramento no Skype para Business Server fornece uma maneira para que os administradores coletar dados de uso e a qualidade das sessões de comunicação que ocorrem em sua organização, que permite que eles identificar tendências e problemas. Monitoramento contínuo da sua implantação permite identificar problemas logo e manter os usuários da organização satisfeito.

Monitoramento no Skype para Business Server não exige uma função de servidor separado (como era o caso em versões anteriores do Lync); em vez disso, o serviço de monitoramento está incluído em cada servidor Front-End. Monitoramento não está habilitado por padrão no Skype para Business Server. Este artigo ajudará você a determinar se deseja habilitar o monitoramento durante ou após sua Skype inicial para configuração do servidor de negócios e quais recursos do SQL que você precisa oferecer suporte a atividades de monitoramento. Se você não tiver certeza exatamente o que é ou não é monitorado e como o monitoramento pode ser úteis, vá para [Noções básicas sobre o monitoramento](monitoring.md#Basics). Para começar o processo de planejamento, vá para [definir as necessidades de monitoramento](monitoring.md#requirements). Para obter mais detalhes sobre os requisitos de SQL de monitoramento, vá para [requisitos do SQL para monitoring](monitoring.md#topologies).

## <a name="basics-about-monitoring"></a>Noções básicas de monitoramento
<a name="Basics"> </a>

Uma sessão é um termo genérico para conexão de um usuário para r:

- Uma conferência

- Uma ferramenta de conferência, como áudio/vídeo ou compartilhamento de aplicativos

- um outro usuário em uma conversa ponto a ponto, como mensagens instantâneas ou uma chamada de áudio

> [!NOTE]
> Skype para Business Server mantém o controle das informações sobre cada sessão: quem chamou quem; pontos de extremidade que foram usados na sessão; quanto tempo a sessão durar; qual foi a qualidade perceptivelmente da sessão; e assim por diante. Skype para Business Server não registrar e armazenar a chamada propriamente dita. Que inclui sessões de mensagens instantâneas: Embora Skype para Business Server registra informações sobre sessões de mensagens instantâneas, ele não mantém um registro de cada mensagem instantânea que foi enviada durante a sessão.

As informações de detalhe de chamada básica coletadas pelo Skype para Business Server para cada sessão podem ser usadas para:

- **Retorno sobre o investimento (ROI)**. Os administradores podem comparar os dados de uso para dados semelhantes coletados para seu sistema de telefonia anterior para mostrar a economia de custos e ajudar a justifica a implantação do Skype para Business Server.

- **Gerenciamento de estoque de dispositivos**. As informações de gerenciamento de ativos ajudam os administradores a identificar dispositivos antigos ainda em uso que precisam ser substituídos, além de identificar dispositivos caros que não são usados ou são subutilizados.

- **Suporte técnico**. Solucionando problemas de dados ajudam suporte engenheiros determinam o motivo pelo qual um usuário de chamada com falha, sem precisar coletar logs do lado servidor ou cliente. Essas informações podem ser acessadas e compreendidas pela equipe de suporte que não têm um conhecimento técnico profundo do Skype para o cliente de negócios e Skype para Business Server prontamente.

- **Solução de problemas de sistemas**. Habilita os administradores a detectar problemas graves que podem impedir os usuários de executar tarefas básicas, como ingressar em uma conferência, estabelecer uma chamada ou enviar uma mensagem instantânea.

Também Monitoring fornece um mecanismo que permite que os pontos de extremidade SIP (por exemplo, o Skype para negócios) para fornecer informações de solução de problemas que o administrador não teriam acesso a:

- **Métricas de mídia que influenciam a qualidade**. Essas métricas lidam com a transmissão da chamada propriamente dita, ou seja, elas fornecem um log de trajeto à medida que a chamada passa pela rede. Essas métricas, que incluem itens como perda de pacotes, tremulação e tempo da viagem de ida e volta, fornecem informações sobre o que aconteceu com a chamada do momento que ela saiu do ponto de extremidade de uma pessoa até o momento que ela chegou ao ponto de extremidade da outra pessoa.

- **Problemas comunicados ao usuário final**. Esses indicadores incluem notificações de baixa qualidade que Skype para negócios apresenta aos usuários finais em casos onde eles estão longe demais de um microfone, falando muito baixo, tem uma conexão de rede ruim, ou estão experimentando baixa qualidade porque outro programa no computador está consumindo os recursos disponíveis.

- **Informações sobre o ambiente**. Essas métricas detalham fatores de qualidade das chamadas, como tipo de microfone e alto-falantes usados e se o usuário está conectado através de uma VPN ou de uma rede sem fio.

No final de cada chamada, os pontos de extremidade compatíveis com SIP transmitem essas informações para o Servidor Front-End que intermediou a chamada. Não é necessária nenhuma ação para que os pontos de extremidade transmitam essas informações, pois esse comportamento já está incorporado ao protocolo SIP. No entanto, se desejar coletar e armazenar essas informações, você precisará instalar e habilitar o monitoramento. Se fizer isso, as informações das chamadas serão coletadas pelos agentes em execução no Servidor Front-End e transmitidas para um par de bancos de dados do SQL Server. O serviço de monitoramento (na forma de "agentes de coleta de dados unificados") é colocado em todos os Servidores Front-End. 

## <a name="define-your-requirements-for-monitoring"></a>Definir seus requisitos de monitoramento
<a name="requirements"> </a>

Ainda há várias principais questões que devem ser resolvidos antes de começar a instalar e configurar o monitoramento com Skype para Business Server:

 **Quando você deseja instalar o monitoramento?** Monitoramento pode ser instalado e configurado ao mesmo tempo instalar e configurados Skype para Business Server. o Skype para o Assistente de implantação do Business Server fornecerá a você a oportunidade para associar os pools de Front-End um banco de dados de monitoramento durante a instalação. Como alternativa, você pode instalar o monitoring após ter sido instalado Skype para Business Server em si; Isso pode ser feito usando o construtor de topologias para associar seus pools de Front-End e servidores de um banco de dados de monitoramento e, em seguida, publicar a topologia revisada.

Lembre-se de que o SQL Server deve ser instalado e configurado antes da implantação e configuração do monitoramento. No entanto, você só precisa para implantar o SQL Server em si; os bancos de dados de monitoramento serão criados para você quando você publica seu Skype para a topologia de servidor de negócios.

 **Que tipo de dados você deseja monitorar?** Skype para Business Server permite monitorar dois tipos gerais de dados: chamada detalhando dados recording (CDR) e dados de qualidade da experiência (QoE). Registro de detalhes da chamada fornece uma maneira de rastrear o uso do Skype para recursos de Business Server, como voz sobre IP (VoIP) de telefonemas; mensagens instantâneas (IM); transferências de arquivos; áudio/vídeo (A / V) conferência; e sessões de compartilhamento de aplicativo. Essa informação ajuda você a saber qual Skype para recursos de Business Server estão sendo usados (e quais não são os) e também fornece informações como para quando esses recursos estão sendo usados. Dados qualidade da experiência permite manter um registro da qualidade das chamadas de áudio e vídeos feitas em sua organização, incluindo coisas como o número de pacotes de rede perdidos, ruído de fundo e a quantidade de "tremulação" (diferenças em atraso do pacote).

Se você optar por habilitar monitoramento no Skype para Business Server, é possível habilitar o monitoramento de CDR e QoE monitoring, ou você pode optar por habilitar um tipo de monitoramento, deixando o outro tipo desabilitado. Por exemplo, suponha que seus usuários usem apenas as mensagens instantâneas e a transferência de arquivos e não façam chamadas de áudio nem vídeo. Nesse caso, pode não haver motivo para habilitar o monitoramento de QoE. Da mesma forma, o Skype para Business Server facilita habilitar e desabilitar o monitoramento após a implantação do monitoring. Por exemplo, você pode escolher implantar o monitoramento, mas deixar o monitoramento de QoE desabilitado a princípio. Se seus usuários começarem a enfrentar problemas com chamadas de áudio e vídeo, você pode habilitar o monitoramento de QoE e usar esses dados para ajudar você a resolver os problemas.

Não há nenhuma vantagem específica (ou desvantagem) instalando o monitoramento ao mesmo tempo em que você instalar o Skype para Business Server versus instalando o monitoramento depois Skype para Business Server tiver sido instalado. É um ponto em mente que, antes de você instala o monitoramento, você deve selecionar um computador hospede backend do repositório de monitoramento e uma versão compatível do SQL Server deve ser configurado no computador e instalar antes desse computador possa ser usado para monitoramento . Se você já instalou o SQL Server em um computador e o computador está pronto para uso, em seguida, você pode instalar monitoramento ao mesmo tempo em que você instale o Skype para Business Server. Se você não tiver um computador back-end pronto você pode continuar e instalar o Skype para Business Server por si só e instalar o monitoring sempre que o computador back-end está pronto para uso.

 **De quantos bancos de dados de monitoramento de back-end você precisa?** Ele foi estimado que um banco de dados colocado para monitoramento e arquivamento poderia suporte 240.000 Skype para usuários corporativos Server). Além disso, um único banco de dados de monitoramento pode ser usado por vários Pools de Front-Ends; se você tem três Pools de Front-Ends em sua organização, é possível associar todos os três ao mesmo repositório de back-end.

Para muitas organizações, a capacidade do banco de dados não será o fator decisivo ao determinar o número de bancos de dados de monitoramento de back-end necessários. Em vez disso, uma consideração mais importante pode ser a velocidade da rede. Suponha que você tenha três Pools de Front-Ends, mas um deles está localizado em uma conexão de rede lenta. Nesse caso, você pode usar dois bancos de dados de monitoramento: um banco de dados para atender aos dois pools com a conexão de rede boa e um banco de dados separado para atender ao pool com a conexão de rede mais lenta.

Você também deve levar em consideração que Skype para Business Server suporta o uso dos bancos de dados de espelho. O "espelhamento do banco de dados" possibilita manter simultaneamente duas cópias de um banco de dados, com cada banco de dados residindo em um servidor diferente. Qualquer dado de tempo é gravado no banco de dados principal, e o mesmo dado também é gravado no banco de dados espelho. Se o banco de dados primário deve falhar ou caso contrário ficar indisponível, você pode "failover" no banco de dados de espelho, usando uma simple Skype para Business Server PowerShell comando. Por exemplo:

```
Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"
```

Isso é importante para fins de planejamento porque o espelhamento exigirá o dobro do número de bancos de dados exigidos: além de cada banco de dados primário, você precisará de um segundo banco de dados para agir como o espelho.

 **Sua Skype para sites de Business Server preciso suas próprias configurações de monitoramento personalizadas?** Quando você instala o Skype para Business Server também instalar coleções globais de definições de configuração de CDR e QoE; Essas coleções globais oferecem a capacidade de aplicar as mesmas configurações de CDR e QoE para toda sua organização. In many cases, this will be sufficient: often-times you will want, say, to have CDR monitoring enabled for all of your users.

No entanto, em outros momentos você pode aplicar configurações diferentes em sites diferentes. Por exemplo, talvez você queira usar o monitoramento de CDR e QoE em seu site de Redmond, mas usar apenas o monitoramento de CDR em seu site de Dublin. Da mesma forma, você pode querer manter os dados de monitoramento por 60 dias no site de Redmond, mas manter esse tipo de dados por apenas 30 dias no site de Dublin. Skype para Business Server permite que você crie conjuntos separados das definições de configuração de CDR e QoE no escopo do site; Isso permite que você gerencie cada site de forma diferente. Isso habilita o gerenciamento de cada site de uma forma diferente (o que inclui a habilitação e desabilitação do monitoramento, assim como a definição das configurações de gerenciamento, como por quanto tempo os dados devem ser mantidos.)

Observe que você pode tomar essa decisão antes ou depois de implantar o monitoramento. Por exemplo, é possível implantar o monitoramento e gerenciar toda a organização usando as configurações globais. Se você mudar de ideia posteriormente, é possível criar uma coleção separada de configurações para, digamos, o site de Redmond, e usar essas configurações para gerenciar o monitoramento para Redmond. As configurações aplicadas no escopo do site sempre têm prioridade em relação às configurações aplicadas no escopo global. Se você mudar de ideia novamente, basta excluir as definições de configuração aplicadas ao site de Redmond. Quando uma coleção de configurações de site for removida, a coleção global de configurações será aplicada automaticamente para o site.

## <a name="sql-requirements-for-monitoring"></a>Requisitos do SQL para o monitoramento
<a name="topologies"> </a>

Os agentes de coleta de dados unificados são instalados e ativados automaticamente em cada Servidor Front-End quando você habilita o monitoramento. Para as versões suportadas do SQL Server e outros detalhes, consulte [requisitos de servidor para Skype para Business Server 2015](requirements-for-your-environment/server-requirements.md)

Os dados de monitoramento pode compartilhar uma instância do SQL Server com outros tipos de dados. Geralmente, o banco de dados de registro de detalhes das chamadas (LcsCdr) e o banco de dados de qualidade da experiência (QoEMetrics) compartilham a mesma instância SQL. Também é comum que os dois bancos de dados de monitoramento estejam na mesma instância SQL que o banco de dados de arquivamento (LcsLog). O único requisito real relacionado às instâncias do SQL Server é que qualquer instância do SQL Server é limitada ao seguinte:

- Uma instância do Skype para banco de dados de back-end Business Server 2015. Como regra geral, não recomendamos que seu banco de dados de monitoramento seja colocado na mesma instância SQL ou no mesmo computador que o banco de dados de back-end. Embora isso seja tecnicamente possível, há o risco de o banco de dados de monitoramento usar espaço em disco necessário para o banco de dados de back-end.

- Uma instância do banco de dados de registro de detalhes das chamadas.

- Uma instância do banco de dados da Qualidade da Experiência.

- Uma instância do banco de dados de arquivamento.

Em outras palavras, não é possível ter duas instâncias do banco de dados LcsCdr na mesma instância do SQL Server. Se você precisa de várias instâncias do banco de dados LcsCdr, deve configurar várias instâncias do SQL Server.

## <a name="see-also"></a>Confira também


[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
