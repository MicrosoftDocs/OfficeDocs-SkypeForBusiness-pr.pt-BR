---
title: Implantar monitoramento no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: 'Resumo: saiba como implantar o monitoramento no Skype for Business Server.'
ms.openlocfilehash: cbb5fe0974e1b02ce5be472ba91d01221fb7df82
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60764839"
---
# <a name="deploy-monitoring-in-skype-for-business-server"></a>Implantar monitoramento no Skype for Business Server

**Resumo:** Saiba como implantar o monitoramento no Skype for Business Server.

Antes de executar essas tarefas, revise [Plan for monitoring in Skype for Business Server](../../plan-your-deployment/monitoring.md).

Normalmente, você implementará serviços de monitoramento em sua topologia, concluindo as duas etapas a seguir:

1. Habilitando o monitoramento ao mesmo tempo em que você configura um novo pool de Skype for Business Server. (No Skype for Business Server, o monitoramento é habilitado ou desabilitado em um pool por pool.) Observe que você pode habilitar o monitoramento de um pool sem realmente coletar dados de monitoramento, um processo explicado na seção Configuring Call Detail Recording and Quality of Experience Configurações desta documentação.

2. Associando um repositório de monitoramento (ou seja, um banco de dados de monitoramento) ao novo pool. Observe que um único repositório pode ser associado a vários pools. Dependendo do número de usuários hospedados em seus pools de registradores, isso significa que não é necessário configurar um banco de dados de monitoramento separado para cada um dos seus pools. Em vez disso, um único repositório de monitoramento pode ser usado por vários pools.

Embora normalmente seja mais fácil habilitar o monitoramento ao mesmo tempo em que o novo pool é criado, também é possível criar um novo pool com o monitoramento desabilitado. Se o fizer, você pode usar o Construtor de Topologias mais tarde para habilitar o serviço: o Construtor de Topologias fornece uma maneira de habilitar ou desabilitar o monitoramento para um pool ou de associar um pool a um repositório de monitoramento diferente. Tenha em mente que, embora não haja mais uma função de Servidor de Monitoramento, você ainda precisará criar um ou mais armazenamentos de monitoramento: bancos de dados back-end usados para armazenar os dados coletados pelo serviço de monitoramento. Esses bancos de dados back-end podem ser criados usando o Microsoft SQL Server 2008 R2, Microsoft SQL Server 2012, Microsoft SQL Server 2014 ou Microsoft SQL Server 2019.

> [!NOTE]
> Se o monitoramento tiver sido habilitado para um pool, você poderá desabilitar o processo de coleta de dados de monitoramento sem precisar alterar sua topologia: o Skype for Business Server fornece uma maneira de desabilitar (e, em seguida, habilitar posteriormente) o CDR (Registro de Detalhes de Chamada) ou a coleta de dados de Qualidade da Experiência (QoE). Para mais informações, consulte a seção Como Configurar o Registro de Detalhes de Chamadas e Configurações de Qualidade de Experiência deste documento.

Outro aprimoramento importante para o monitoramento no Skype for Business Server é o fato de que os Relatórios de Monitoramento do Skype for Business Server agora suportam IPv6: os relatórios que usam o campo Endereço IP exibirão endereços IPv4 ou IPv6 dependendo de : 1) a consulta SQL sendo usada; e, 2) onde o endereço IPv6 está ou não armazenado no banco de dados de monitoramento.

> [!NOTE]
> Verifique se o tipo de inicialização do serviço de agente do SQL Server é Automático e se o Serviço de Agente do SQL Server está em execução para a Instância do SQL que está segurando os bancos de dados de Monitoramento, para que os Trabalhos de Manutenção padrão do SQL Server possam ser executados com base no agendamento sob o controle do serviço SQL Server Agent.

Esta documentação orienta você sobre o processo de instalação e configuração de relatórios de monitoramento e monitoramento para Skype for Business Server. A documentação fornece instruções passo a passo que o ajudarão a:

- Habilitar o monitoramento na sua topologia e associar um repositório de monitoramento a um pool de Front End.

- Instale SQL Server Reporting Services e os relatórios Skype for Business Server monitoramento. Relatórios de Monitoramento são relatórios pré-configurados que fornecem visões diferentes das informações armazenadas em um banco de dados de monitoramento.

- Configure a cdr (registro de detalhes de chamada) e a coleta de dados qualidade da experiência (QoE). A gravação de detalhes de chamadas fornece uma maneira de rastrear o uso de recursos Skype for Business Server como chamadas telefônicas VoIP (Voz sobre IP). mensagens instantâneas (IM); transferências de arquivos; conferência de áudio/vídeo (A/V); e sessões de compartilhamento de aplicativos. Métricas de QoE rastreiam a qualidade de chamadas de áudio/vídeo feitas em sua organização, incluindo itens como o número de pacotes de rede perdidos, ruídos de fundo e o volume de "tremulação" (diferenças no intervalo de pacotes).

- Limpar manualmente registros de CDR e/ou QoE do banco de dados de monitoramento.

## <a name="deployment-checklist-for-monitoring"></a>Lista de verificação de implantação para monitoramento

Embora o monitoramento já esteja instalado e ativado em cada servidor Front-End, ainda há várias etapas que você deve realizar antes de poder realmente coletar dados de monitoramento para Skype for Business Server. Essas etapas são descritas na seguinte lista de verificação:

|**Fase**|**Etapas**|**Função e associação de grupo**|**Documentação**|
|:-----|:-----|:-----|:-----|
|**Instale o pré-requisito de hardware e software** <br/> |Instale uma versão do Microsoft SQL Server suportada no computador que atuará como armazenamento de dados backend do monitoramento.  <br/> |Usuário do domínio que também é membro do grupo local de administradores.  <br/> |[Hardware suportado](/previous-versions/office/lync-server-2013/lync-server-2013-supported-hardware) <br/> [Suporte de infraestrutura e software do servidor](/previous-versions/office/lync-server-2013/lync-server-2013-server-software-and-infrastructure-support) <br/> |
|**Criar a topologia interna apropriada para dar suporte ao monitoramento** <br/> |Use Skype for Business Server Construtor de Topologias para adicionar bancos de dados de monitoramento à topologia e, em seguida, publicou a topologia atualizada.  <br/> |Para definir uma topologia, um usuário que seja membro do grupo local de usuários.  <br/> Para publicar a topologia, um usuário que seja membro do grupo de administradores de domínio e do grupo RTCUniversalServerAdmins.  <br/> |[Associar um armazenamento de monitoramento a um pool de Front-End no Skype for Business Server](associate-a-monitoring-store.md) <br/> |
|**Habilitar a configuração de monitoramento apropriada** <br/> |Habilitar o monitoramento cdr (registro de detalhes de chamada) e/ou qualidade da experiência (QoE) nos escopos global e/ou de site.  <br/> |Um usuário que seja membro do grupo RTCUniversalServerAdmins ou que tenha sido atribuído a uma função RBAC que fornece acesso aos cmdlets CsCdrConfiguration e CsQoEConfiguration .  <br/> |[Configurar o registro de detalhes de chamada e as configurações de Qualidade da Experiência no Skype for Business Server](call-detail-recording-and-qoe.md) <br/> |

## <a name="enable-monitoring"></a>Habilitar o monitoramento

Embora os agentes de coleta de dados unificados sejam instalados e ativados automaticamente em cada servidor Front-End, isso não significa que você começará automaticamente a coletar dados de monitoramento no momento em que terminar de instalar o Skype for Business Server. Em vez disso, você deve fazer duas coisas: você deve associar seus servidores front-end/pools de front-end a um banco de dados de monitoramento e deve habilitar o CDR (Registro de Detalhes de Chamada) e/ou o monitoramento de Qualidade da Experiência (QoE) no escopo global e/ou no escopo do site.

Para obter instruções passo a passo sobre como associar servidores Front-End ou pools de Front-End a um banco de dados de monitoramento, consulte o tópico Associar um armazenamento de monitoramento a um [pool de Front-End](associate-a-monitoring-store.md) no Skype for Business Server no guia implantação. Depois que essas associações foram feitas e depois que sua nova topologia de Skype for Business Server tiver sido publicada, você ainda não poderá coletar dados de monitoramento. Isso porque, por padrão, a coleção de dados CDR e QoE é desabilitada quando você instala Skype for Business Server.

Para poder começar a coletar dados necessários habilite o CDR e/ou monitoramento QoE. (Observe que você não precisa habilitar o monitoramento de CDR e QoE; se preferir, você pode habilitar um tipo de monitoramento enquanto deixa o outro tipo desabilitado.) Para habilitar o monitoramento de CDR no escopo global, execute o seguinte comando no Shell de Gerenciamento Skype for Business Server:

```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

Como alternativa, você pode habilitar o monitoramento de CDR de dentro do painel Skype for Business Server Controle. De dentro do Skype for Business Server De controle, conclua o seguinte procedimento:

1. Clique em **Monitoramento**.

2. Na guia **Registro de Detalhes da Chamada**, clique duas vezes na configuração **Global**.

3. No painel **Editar configuração do registro de detalhe da chamada (CDR)**, selecione **Habilitar monitoramento de CDRs** e clique em **Confirmar**.

Para habilitar o monitoramento de QoE no escopo global, execute este comando no Shell de Gerenciamento Skype for Business Server:

```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

Se preferir, você também pode habilitar o monitoramento de QoE de dentro do painel Skype for Business Server Controle. No Painel de Controle, conclua o seguinte procedimento:

1. Clique em **Monitoramento**.

2. Na guia **Dados da Qualidade da Experiência**, clique duas vezes na configuração **Global**.

3. No painel **Editar configuração da Qualidade da Experiência (QoE)**, selecione **Habilitar monitoramento de dados QoE** e clique em **Confirmar**.

Como observado, os exemplos anteriores habilitam o monitoramento no escopo global; isto é, eles habilitam o monitoramento CDR e QoE através da sua organização. Em alternativa, é possível criar definições de configurações CDR e QoE separadas no escopo local e habilitar ou desabilitar seletivamente o monitoramento de cada local. Por exemplo, é possível habilitar o monitoramento CDR para seu local Redmond, desabilitar o monitoramento CDR para Dublin. Para obter mais informações sobre como gerenciar suas configurações de monitoramento, consulte o tópico Guia de implantação Configurar o registro de detalhes da chamada e as configurações de Qualidade da Experiência [no Skype for Business Server](call-detail-recording-and-qoe.md).

## <a name="see-also"></a>Confira também

[Planejar o monitoramento em Skype for Business Server](../../plan-your-deployment/monitoring.md)