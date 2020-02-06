---
title: Planejar o monitoramento no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
description: 'Resumo: revise este tópico ao planejar o serviço de monitoramento no Skype for Business Server.'
ms.openlocfilehash: 6089997a606463b93e7ae68a2cf080f1bb58ebc1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815799"
---
# <a name="plan-for-monitoring-in-skype-for-business-server"></a>Planejar o monitoramento no Skype for Business Server

**Resumo:** Revise este tópico ao planejar o serviço de monitoramento no Skype for Business Server.

O serviço de monitoramento no Skype for Business Server oferece uma maneira para os administradores coletarem dados de uso e de qualidade para as sessões de comunicação que ocorrem na organização, o que permite identificar tendências e problemas. O monitoramento contínuo da sua implantação permite que você capture problemas antes e mantenha os usuários da sua organização satisfeitos.

O monitoramento no Skype for Business Server não requer uma função de servidor separada (como era o caso nas versões anteriores do Lync); em vez disso, o serviço de monitoramento é integrado a cada servidor front-end. O monitoramento não é habilitado por padrão no Skype for Business Server. Este artigo ajudará você a determinar se deseja habilitar o monitoramento durante ou após a configuração inicial do Skype for Business Server e quais recursos do SQL você precisará para dar suporte a atividades de monitoramento. Se você não tiver certeza de que exatamente o que está ou não é monitorado e como o monitoramento pode ser útil, acesse [noções básicas sobre monitoramento](monitoring.md#Basics). Para começar o processo de planejamento, vá para [definir suas necessidades de monitoramento](monitoring.md#requirements). Para obter mais detalhes sobre os requisitos do SQL para monitoramento, acesse [requisitos do SQL para monitoramento](monitoring.md#topologies).

## <a name="basics-about-monitoring"></a>Noções básicas de monitoramento
<a name="Basics"> </a>

Uma sessão é um termo genérico para a conexão de um usuário a:

- Uma conferência

- Uma ferramenta de conferência, como áudio/vídeo ou compartilhamento de aplicativos

- um outro usuário em uma conversa ponto a ponto, como mensagens instantâneas ou uma chamada de áudio

> [!NOTE]
> O Skype for Business Server mantém o controle das informações sobre cada sessão: quem chamou quem; quais pontos de extremidade foram usados na sessão; Qual foi a duração da sessão por último; Qual foi a qualidade percebida da sessão; e assim por diante. O Skype for Business Server não grava e armazena a chamada propriamente dita. Isso inclui sessões de mensagens instantâneas: embora o Skype for Business Server Registre informações sobre sessões de mensagens instantâneas, ele não mantém um registro de cada mensagem instantânea enviada durante a sessão.

As informações básicas de chamadas detalhadas coletadas pelo Skype for Business Server para cada sessão podem ser usadas para:

- **Retorno sobre o investimento (ROI)**. Os administradores podem comparar os dados de uso com dados similares coletados para o sistema de telefonia anterior a fim de mostrar a economia de custos e ajudar a justificar a implantação do Skype for Business Server.

- **Gerenciamento de estoque de dispositivos**. As informações de gerenciamento de ativos ajudam os administradores a identificar dispositivos antigos ainda em uso que precisam ser substituídos, além de identificar dispositivos caros que não são usados ou são subutilizados.

- **Suporte técnico**. A solução de problemas de dados ajuda os engenheiros de suporte a determinar por que a chamada do usuário falhou, sem precisar coletar os logs do lado do servidor ou do cliente. Essas informações podem ser acessadas de forma imediata e compreendidas pela equipe de suporte que não tenha um conhecimento técnico profundo do cliente Skype for Business e do Skype for Business Server.

- **Solução de problemas de sistemas**. Habilita os administradores a detectar problemas graves que podem impedir os usuários de executar tarefas básicas, como ingressar em uma conferência, estabelecer uma chamada ou enviar uma mensagem instantânea.

O monitoramento também fornece um mecanismo que permite pontos de extremidade SIP (como o Skype for Business), para fornecer informações de solução de problemas às quais o administrador não teria acesso a:

- **Métricas de mídia que influenciam a qualidade**. Essas métricas lidam com a transmissão da chamada propriamente dita, ou seja, elas fornecem um log de trajeto à medida que a chamada passa pela rede. Essas métricas, que incluem itens como perda de pacotes, tremulação e tempo da viagem de ida e volta, fornecem informações sobre o que aconteceu com a chamada do momento que ela saiu do ponto de extremidade de uma pessoa até o momento que ela chegou ao ponto de extremidade da outra pessoa.

- **Problemas comunicados ao usuário final**. Essas métricas incluem notificações de baixa qualidade que o Skype for Business apresenta aos usuários finais em casos em que eles estão longe de um microfone, falar muito sem problemas, ter uma conexão de rede deficiente ou ter baixa qualidade porque outro programa na computador está consumindo os recursos disponíveis.

- **Informações sobre o ambiente**. Essas métricas detalham fatores de qualidade das chamadas, como tipo de microfone e alto-falantes usados e se o usuário está conectado através de uma VPN ou de uma rede sem fio.

No final de cada chamada, os pontos de extremidade compatíveis com SIP transmitem essas informações para o Servidor Front-End que intermediou a chamada. Não é necessária nenhuma ação para que os pontos de extremidade transmitam essas informações, pois esse comportamento já está incorporado ao protocolo SIP. No entanto, se desejar coletar e armazenar essas informações, você precisará instalar e habilitar o monitoramento. Se fizer isso, as informações das chamadas serão coletadas pelos agentes em execução no Servidor Front-End e transmitidas para um par de bancos de dados do SQL Server. O serviço de monitoramento (na forma de "agentes de coleta de dados unificados") é colocado em todos os Servidores Front-End. 

## <a name="define-your-requirements-for-monitoring"></a>Definir seus requisitos de monitoramento
<a name="requirements"> </a>

Ainda há vários problemas importantes que devem ser resolvidos antes de começar a instalar e configurar o monitoramento com o Skype for Business Server:

 **Quando você deseja instalar o monitoramento?** A monitoração pode ser instalada e configurada ao mesmo tempo em que você instala e configurou o Skype for Business Server; o assistente de implantação do Skype for Business Server oferece a você a oportunidade de associar seus pools de front-end a um banco de dados de monitoramento durante a configuração. Você também pode instalar o monitoramento após a instalação do Skype for Business Server. Isso pode ser feito usando o construtor de topologias para associar seus pools e servidores de front-end a um banco de dados de monitoramento e, em seguida, publicar a topologia revisada.

Lembre-se de que o SQL Server deve ser instalado e configurado antes da implantação e configuração do monitoramento. No entanto, você só precisa implantar o próprio SQL Server; os bancos de dados de monitoramento serão criados para você quando você publicar a topologia do Skype for Business Server.

 **Que tipo de dados você deseja monitorar?** O Skype for Business Server permite que você monitore dois tipos gerais de dados: dados de registros de detalhes de chamadas (CDR) e dados de qualidade da experiência (QoE). A gravação de detalhes da chamada fornece uma maneira de acompanhar o uso de recursos do Skype for Business Server, como chamadas telefônicas de voz sobre IP (VoIP); mensagens instantâneas (IM); transferências de arquivos; Conferência de áudio/vídeo (A/V); e sessões de compartilhamento de aplicativos. Essas informações ajudam você a saber quais recursos do Skype for Business Server estão sendo usados (e quais não são) e também fornece informações sobre quando esses recursos estão sendo usados. Os dados de qualidade da experiência permitem que você mantenha um registro da qualidade das chamadas de áudio e de vídeo feitas em sua organização, incluindo itens como o número de pacotes de rede perdidos, o ruído de fundo e a quantidade de "tremulação" (diferenças no atraso do pacote).

Se optar por habilitar o monitoramento no Skype for Business Server, você poderá habilitar o monitoramento de CDR e o monitoramento de QoE, ou poderá optar por habilitar um tipo de monitoramento e deixar o outro tipo desabilitado. Por exemplo, suponha que seus usuários usem apenas as mensagens instantâneas e a transferência de arquivos e não façam chamadas de áudio nem vídeo. Nesse caso, pode não haver motivo para habilitar o monitoramento de QoE. Da mesma forma, o Skype for Business Server facilita a ativação e a desativação do monitoramento após a implantação do monitoramento. Por exemplo, você pode escolher implantar o monitoramento, mas deixar o monitoramento de QoE desabilitado a princípio. Se seus usuários começarem a enfrentar problemas com chamadas de áudio e vídeo, você pode habilitar o monitoramento de QoE e usar esses dados para ajudar você a resolver os problemas.

Não há nenhuma vantagem específica (ou desvantagem) de instalar o monitoramento ao mesmo tempo em que você instala o Skype for Business Server versus a instalação do monitoramento após a instalação do Skype for Business Server. O ponto único a ter em mente é que, antes de instalar o monitoramento, você deve selecionar um computador para hospedar o armazenamento de monitoramento de back-end e uma versão com suporte do SQL Server deve estar instalada e configurada nesse computador para que o computador possa ser usado para monitoramento . Se você já tiver instalado o SQL Server em um computador e esse computador estiver pronto para uso, você poderá instalar o monitoramento ao mesmo tempo em que instala o Skype for Business Server. Se você não tiver um computador back-end pronto, pode prosseguir para instalar o Skype for Business Server por si só e instalar o monitoramento sempre que o computador back-end estiver pronto para uso.

 **De quantos bancos de dados de monitoramento de back-end você precisa?** Estima-se que um banco de dados posicionado para monitoramento e arquivamento possa dar suporte a 240.000 usuários do Skype for Business Server). Além disso, um único banco de dados de monitoramento pode ser usado por vários Pools de Front-Ends; se você tem três Pools de Front-Ends em sua organização, é possível associar todos os três ao mesmo repositório de back-end.

Para muitas organizações, a capacidade do banco de dados não será o fator decisivo ao determinar o número de bancos de dados de monitoramento de back-end necessários. Em vez disso, uma consideração mais importante pode ser a velocidade da rede. Suponha que você tenha três Pools de Front-Ends, mas um deles está localizado em uma conexão de rede lenta. Nesse caso, você pode usar dois bancos de dados de monitoramento: um banco de dados para atender aos dois pools com a conexão de rede boa e um banco de dados separado para atender ao pool com a conexão de rede mais lenta.

Você também deve levar em conta que o Skype for Business Server oferece suporte ao uso de bancos de dados espelhados. O "espelhamento do banco de dados" possibilita manter simultaneamente duas cópias de um banco de dados, com cada banco de dados residindo em um servidor diferente. Qualquer dado de tempo é gravado no banco de dados principal, e o mesmo dado também é gravado no banco de dados espelho. Se o banco de dados primário não funcionar ou se tornar indisponível, você pode "fazer failover" para o banco de dados espelho usando um comando do PowerShell do Skype for Business Server simples. Por exemplo:

```PowerShell
Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"
```

Isso é importante para fins de planejamento porque o espelhamento exigirá o dobro do número de bancos de dados exigidos: além de cada banco de dados primário, você precisará de um segundo banco de dados para agir como o espelho.

 **Seus sites do Skype for Business Server precisam de suas próprias configurações de monitoramento personalizado?** Ao instalar o Skype for Business Server, você também pode instalar coleções globais das configurações de configuração de CDR e QoE; Essas coleções globais dão a você a capacidade de aplicar as mesmas configurações de CDR e QoE para toda a sua organização. In many cases, this will be sufficient: often-times you will want, say, to have CDR monitoring enabled for all of your users.

No entanto, em outros momentos você pode aplicar configurações diferentes em sites diferentes. Por exemplo, talvez você queira usar o monitoramento de CDR e QoE em seu site de Redmond, mas usar apenas o monitoramento de CDR em seu site de Dublin. Da mesma forma, você pode querer manter os dados de monitoramento por 60 dias no site de Redmond, mas manter esse tipo de dados por apenas 30 dias no site de Dublin. O Skype for Business Server permite que você crie coleções separadas das configurações de configuração de CDR e QoE no escopo do site; Isso permite que você gerencie cada site de forma diferente. Isso habilita o gerenciamento de cada site de uma forma diferente (o que inclui a habilitação e desabilitação do monitoramento, assim como a definição das configurações de gerenciamento, como por quanto tempo os dados devem ser mantidos.)

Observe que você pode tomar essa decisão antes ou depois de implantar o monitoramento. Por exemplo, é possível implantar o monitoramento e gerenciar toda a organização usando as configurações globais. Se você mudar de ideia posteriormente, é possível criar uma coleção separada de configurações para, digamos, o site de Redmond, e usar essas configurações para gerenciar o monitoramento para Redmond. As configurações aplicadas no escopo do site sempre têm prioridade em relação às configurações aplicadas no escopo global. Se você mudar de ideia novamente, basta excluir as definições de configuração aplicadas ao site de Redmond. Quando uma coleção de configurações de site for removida, a coleção global de configurações será aplicada automaticamente para o site.

## <a name="sql-requirements-for-monitoring"></a>Requisitos do SQL para o monitoramento
<a name="topologies"> </a>

Os agentes de coleta de dados unificados são instalados e ativados automaticamente em cada Servidor Front-End quando você habilita o monitoramento. Para as versões compatíveis do SQL Server e outros detalhes, consulte [requisitos do servidor para o Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)

Os dados de monitoramento pode compartilhar uma instância do SQL Server com outros tipos de dados. Geralmente, o banco de dados de registro de detalhes das chamadas (LcsCdr) e o banco de dados de qualidade da experiência (QoEMetrics) compartilham a mesma instância SQL. Também é comum que os dois bancos de dados de monitoramento estejam na mesma instância SQL que o banco de dados de arquivamento (LcsLog). O único requisito real relacionado às instâncias do SQL Server é que qualquer instância do SQL Server é limitada ao seguinte:

- Uma instância do banco de dados back-end do Skype for Business Server 2015. Como regra geral, não recomendamos que seu banco de dados de monitoramento seja colocado na mesma instância SQL ou no mesmo computador que o banco de dados de back-end. Embora isso seja tecnicamente possível, há o risco de o banco de dados de monitoramento usar espaço em disco necessário para o banco de dados de back-end.

- Uma instância do banco de dados de registro de detalhes das chamadas.

- Uma instância do banco de dados da Qualidade da Experiência.

- Uma instância do banco de dados de arquivamento.

Em outras palavras, não é possível ter duas instâncias do banco de dados LcsCdr na mesma instância do SQL Server. Se você precisa de várias instâncias do banco de dados LcsCdr, deve configurar várias instâncias do SQL Server.

## <a name="see-also"></a>Confira também


[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
