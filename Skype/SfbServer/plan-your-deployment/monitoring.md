---
title: Planejar o monitoramento em Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
description: 'Resumo: revise este tópico durante o planejamento do serviço de monitoramento no Skype for Business Server.'
ms.openlocfilehash: 215402fa68c89d6484532b0c6e7fb6093f591b23
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62404583"
---
# <a name="plan-for-monitoring-in-skype-for-business-server"></a>Planejar o monitoramento em Skype for Business Server

**Resumo:** Revise este tópico durante o planejamento do serviço de monitoramento Skype for Business Server.

O serviço de monitoramento no Skype for Business Server fornece uma maneira para os administradores coletarem dados de uso e qualidade para as sessões de comunicação que ocorrem em sua organização, o que permite identificar tendências e problemas. O monitoramento contínuo de sua implantação permite que você pegue problemas no início e mantenha os usuários da sua organização satisfeitos.

O monitoramento no Skype for Business Server não exige uma função de servidor separada (como era o caso nas versões anteriores do Lync); em vez disso, o serviço de monitoramento é integrado a cada servidor Front-End. O monitoramento não está habilitado por padrão no Skype for Business Server. Este artigo ajudará você a determinar se deve habilitar o Monitoramento durante ou após a configuração inicial Skype for Business Server e quais recursos SQL você precisará para dar suporte às atividades de Monitoramento. Se você não tiver certeza do que é ou não monitorado e como o monitoramento pode ser útil, acesse [Noções básicas sobre Monitoramento](monitoring.md#Basics). Para começar seu processo de planejamento, vá para [Definir seus requisitos para monitoramento](monitoring.md#requirements). Para obter mais detalhes sobre os SQL de monitoramento, acesse SQL [requisitos de monitoramento](monitoring.md#topologies).

## <a name="basics-about-monitoring"></a>Noções básicas sobre Monitoramento
<a name="Basics"> </a>

Uma sessão é um termo genérico para a conexão de um usuário com um:

- Conferência

- Ferramenta de conferência como Áudio/Vídeo ou Compartilhamento de Aplicativos

- Outro usuário em uma conversa ponto a ponto, como mensagens instantâneas ou uma chamada de áudio

> [!NOTE]
> Skype for Business Server mantém o controle de informações sobre cada sessão: quem chamou quem; quais pontos de extremidade foram usados na sessão; por quanto tempo a sessão foi passada; qual foi a qualidade percebida da sessão; e assim por diante. Skype for Business Server não registra e armazena a chamada real em si. Isso inclui sessões de mensagens instantâneas: embora Skype for Business Server registra informações sobre sessões de mensagens instantâneas, ela não mantém um registro de cada mensagem instantânea que foi enviada durante a sessão.

As informações básicas de detalhes de chamada coletadas por Skype for Business Server para cada sessão podem ser usadas para:

- **Análise de Retorno sobre Investimento (ROI** ). Os administradores podem comparar os dados de uso com dados semelhantes coletados para seu sistema de telefonia anterior para mostrar a economia de custos e ajudar a justificar a implantação de Skype for Business Server.

- **Gerenciamento de inventário de dispositivos**. As informações de gerenciamento de ativos ajudam os administradores a identificar dispositivos antigos ainda em uso que precisam ser substituídos e identificar dispositivos caros que não são usados ou subutilizáveis.

- **Suporte Técnico**. A solução de problemas de dados ajuda os engenheiros a determinar por que a chamada de um usuário falhou, sem precisar coletar logs do servidor ou do lado do cliente. Essas informações podem ser facilmente acessadas e compreendidas pela equipe de suporte que não têm um profundo conhecimento técnico do cliente Skype for Business e Skype for Business Server.

- **Solução de problemas de sistemas**. Permite que os administradores detectem problemas graves que podem impedir que os usuários executem tarefas básicas, como ingressar em uma conferência, estabelecer uma chamada ou enviar uma mensagem instantânea.

O monitoramento também fornece um mecanismo que permite que os pontos de extremidade SIP (como Skype for Business) forneçam informações de solução de problemas que o administrador não teria acesso a:

- **Métricas de mídia que influenciam a qualidade**. Essas métricas lidam com a transmissão real da chamada em si; eles fornecem uma espécie de travelogue como as viagens de chamada pela rede. Essas métricas (que incluem coisas como perda de pacotes, tremidos e tempos de ida e volta) fornecem informações sobre o que aconteceu com a chamada desde o momento em que ela deixou o ponto de extremidade de uma pessoa até o momento em que chegou ao ponto de extremidade da outra pessoa.

- **Problemas comunicados ao usuário final**. Essas métricas incluem notificações de baixa qualidade que o Skype for Business apresenta aos usuários finais em casos em que eles estão muito longe de um microfone, falando muito suavemente, têm uma conexão de rede ruim ou estão enfrentando uma má qualidade porque outro programa no computador está consumindo os recursos disponíveis.

- **Informações sobre o ambiente**. Essas métricas detalham fatores de qualidade das chamadas, como tipo de microfone e alto-falantes usados e se o usuário está conectado através de uma VPN ou de uma rede sem fio.

No final de cada chamada, os pontos de extremidade compatíveis com SIP transmitem essas informações para o servidor front-end que facilitou a chamada. Não é necessária nenhuma ação manual para que os pontos de extremidade transmitam essas informações, pois essa função já é incorporada ao protocolo SIP. No entanto, se você desejar coletar e armazenar essas informações, precisará instalar e habilitar o monitoramento. Se fizer isso, as informações sobre as chamadas serão coletadas pelos agentes em execução no servidor front-end e transmitidas para um par de bancos de dados do SQL Server. O serviço de monitoramento (na forma de "agentes unificados de coleta de dados") é alocado em todos os servidores Front-End.

## <a name="define-your-requirements-for-monitoring"></a>Definir seus requisitos para monitoramento
<a name="requirements"> </a>

Ainda há vários problemas importantes que devem ser resolvidos antes de começar a instalar e configurar o monitoramento com Skype for Business Server:

 **Quando você deseja instalar o monitoramento?** O monitoramento pode ser instalado e configurado ao mesmo tempo em que você instala e configura o Skype for Business Server; o Assistente de Implantação do Skype for Business Server oferecerá a oportunidade de associar seus pools de Front-End a um banco de dados de monitoramento durante a instalação. Como alternativa, você pode instalar o monitoramento depois que o próprio Skype for Business Server tiver sido instalado; isso pode ser feito usando o Construtor de Topologias para associar seus pools e servidores front-end a um banco de dados de monitoramento e publicar a topologia revisada.

Lembre-se de que SQL Server deve ser instalado e configurado antes de implantar e configurar o monitoramento. No entanto, você só precisa implantar o SQL Server em si; os bancos de dados de monitoramento serão criados para você quando você publicar sua topologia de Skype for Business Server.

 **Que tipo de dados você deseja monitorar?** Skype for Business Server permite monitorar dois tipos gerais de dados: dados de CDR (registro de detalhes de chamada) e dados de QoE (Qualidade da Experiência). A gravação de detalhes da chamada oferece uma maneira de rastrear o uso de recursos Skype for Business Server como chamadas telefônicas VoIP (Voz sobre IP); mensagens instantâneas (IM); transferências de arquivos; conferência de áudio/vídeo (A/V) e sessões de compartilhamento de aplicativos. Essas informações ajudam você a saber quais Skype for Business Server recursos estão sendo usados (e quais não estão) e também fornece informações sobre quando esses recursos estão sendo usados. Os dados de Qualidade de Experiência permitem que você mantenha um registro da qualidade das chamadas de áudio e vídeo feitas em sua organização, incluindo coisas como o número de pacotes de rede perdidos, o ruído em segundo plano e a quantidade de "tremulagem" (diferenças no atraso do pacote).

Se você optar por habilitar o monitoramento no Skype for Business Server pode habilitar o monitoramento de CDR e o monitoramento de QoE, ou pode optar por habilitar um tipo de monitoramento enquanto deixa o outro tipo desabilitado. Por exemplo, suponha que seus usuários apenas utilizem mensagem instantânea e transferência de arquivos e não realizem chamadas de áudio ou vídeo. Neste caso, pode não haver motivo para habilitar o monitoramento QoE. Da mesma forma, Skype for Business Server torna mais fácil habilitar e desabilitar o monitoramento após a implantação do monitoramento. Por exemplo, você pode escolher implantar o monitoramento, mas deixar inicialmente o monitoramento QoE desabilitado. Se seus usuários começam a enfrentar problemas com chamadas de áudio e vídeo, habilite o monitoramento QoE e use estes dados para ajudar você a resolver problemas.

Não há nenhuma vantagem específica (ou desvantagem) para instalar o monitoramento ao mesmo tempo em que você instala Skype for Business Server vs. instalando o monitoramento após Skype for Business Server tiver sido instalado. O único ponto a lembrar é que, antes de instalar o monitoramento, você deve selecionar um computador para hospedar o repositório de monitoramento de backend e uma versão suportada do SQL Server deve ser instalada e configurada neste computador antes de que possa ser usado para monitoramento. Se você já instalou o SQL Server em um computador e esse computador está pronto para uso, você pode instalar o monitoramento ao mesmo tempo em que instala Skype for Business Server. Se você não tiver um computador back-end pronto, poderá continuar a instalar o Skype for Business Server sozinho e instalar o monitoramento sempre que o computador back-end estiver pronto para uso.

 **Quantos bancos de dados de monitoramento de backend você precisa?** Foi estimado que um banco de dados alocado para monitoramento e arquivamento poderia dar suporte a 240.000 Skype for Business Server usuários). Além disso, um único banco de dados de monitoramento pode ser usado por vários pools de front-end; se você possui três pools de front-end na sua organização, é possível associar todos os três pools com o mesmo repositório de backend.

Para muitas organizações, a capacidade do banco de dados não será o fator decisivo ao determinar o número de bancos de dados de monitoramento de back-end que serão necessários. Ao invés disso, uma consideração mais importante pode ser a velocidade da rede. Suponha que você possui três pools de front-end, mas um destes pools está localizado em uma conexão de rede lenta. Neste caso, você pode desejar usar dois bancos de dados de monitoramento: um banco de dados para serviço dos dois pools com boa conexão de rede e um banco de dados separado para serviço do pool com a conexão de rede mais lenta.

Você também deve levar em conta que o Skype for Business Server dá suporte ao uso de bancos de dados espelho. "Espelhamento do banco de dados" oferece uma forma de manter simultaneamente duas cópias de um banco de dados, cada banco de dados residindo em um servidor diferente. Qualquer dado de tempo é gravado no banco de dados primário que o mesmo dado também é gravado no banco de dados de espelho. Se o banco de dados principal falhar ou ficar indisponível, você poderá "fazer fail over" no banco de dados espelho usando um comando Skype for Business Server PowerShell simples. Por exemplo:

```PowerShell
Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"
```

Isto é importante para fins de planejamento porque o espelhamento exigirá o dobro do número exigido de bancos de dados: além de cada banco de dados primário, você precisará de um segundo banco de dados para agir como o espelho.

 **Seus sites Skype for Business Server precisam de suas próprias configurações de monitoramento personalizadas?** Quando você instala o Skype for Business Server também instala coleções globais de configurações de CDR e QoE; essas coleções globais dão a você a capacidade de aplicar as mesmas configurações de CDR e QoE a toda a sua organização. Em vários casos, isto pode ser suficiente: frequentemente, digamos, se você tiver o monitoramento CDR habilitado para todos os seus usuários.

No entanto, pode haver momentos quando você deseja aplicar configurações diferentes para sites diferentes. Por exemplo, talvez você deseje usar o monitoramento CDR e QoE em seu site Redmond, mas usar apenas o monitoramento CDR em seu site Dublin. Da mesma forma, você pode desejar manter os dados de monitoramento por 60 dias no site Redmond, mas precisa apenas manter este tipo de dados por 30 dias no site Dublin. Skype for Business Server permite que você crie coleções separadas de configurações de CDR e QoE no escopo do site; isso permite que você gerencie cada site de forma diferente. (Isto inclui a habilitação e desabilitação do monitoramento, assim como a definição das configurações de gerenciamento como quanto tempo os dados devem ser mantidos.)

Observe que você pode tomar esta decisão antes de implantar o monitoramento ou após implantar o monitoramento. Por exemplo, é possível implantar o monitoramento e gerenciar toda a organização usando as configurações globais. Se você mudar de ideia posteriormente, é possível criar um conjunto separado de configurações para, digamos, o site Redmond, e usa estas configurações para gerenciar o monitoramento para Redmond. (As configurações aplicadas no escopo do site sempre têm precedência sobre as configurações aplicadas no escopo global.) Se você mudar de ideia novamente, basta excluir as definições de configuração aplicadas ao site Redmond. Quando um conjunto de configurações de site é removido, o conjunto global de configurações será aplicado automaticamente para este site.

## <a name="sql-requirements-for-monitoring"></a>SQL requisitos para monitoramento
<a name="topologies"> </a>

Os agentes de coleta de dados unificados são instalados e ativados automaticamente em cada servidor Front-End quando você habilita o Monitoramento. Para obter versões com suporte de SQL Server e outros detalhes, consulte [Requisitos de servidor para Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)

Os dados de monitoramento podem compartilhar uma SQL Server com outros tipos de dados. Normalmente, o banco de dados de registro de detalhes de chamada (LcsCdr) e o banco de dados de Qualidade da Experiência (QoEMetrics) compartilham a mesma instância SQL; também é comum que os dois bancos de dados de monitoramento sejam na mesma instância SQL que o banco de dados de arquivamento (LcsLog). Sobre o único requisito real com SQL Server instâncias é que qualquer instância de SQL Server está limitada ao seguinte:

- Uma instância do banco de dados de back-Skype for Business Server 2015. (Como regra geral, não é recomendável que seu banco de dados de monitoramento seja alocado na mesma instância SQL ou mesmo no mesmo computador, como o banco de dados back-end. Embora tecnicamente possível, você corre o risco de o banco de dados de monitoramento usar o espaço em disco necessário para o banco de dados back-end.)

- Uma instância do banco de dados de registro de detalhes de chamada.

- Uma instância do banco de dados qualidade da experiência.

- Uma instância do banco de dados de arquivamento.

Em outras palavras, você não pode ter duas instâncias do banco de dados LcsCdr na mesma instância de SQL Server. Se você precisar de várias instâncias do banco de dados LcsCdr, precisará configurar várias instâncias de SQL Server.

## <a name="see-also"></a>Confira também


[Implantando o monitoramento](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)