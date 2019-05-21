---
title: Implantar o monitoramento no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: 'Resumo: saiba como implantar o monitoramento no Skype for Business Server.'
ms.openlocfilehash: bd194e8f39130de7a02a56afa2fa1f82bb662c76
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282378"
---
# <a name="deploy-monitoring-in-skype-for-business-server"></a>Implantar o monitoramento no Skype for Business Server

**Resumo:** Saiba como implantar o monitoramento no Skype for Business Server.

Antes de executar essas tarefas, revisar o [plano para monitorar o Skype for Business Server](../../plan-your-deployment/monitoring.md).

Geralmente, você implementará serviços de monitoramento em sua topologia concluindo as duas etapas a seguir:

1. Habilitar o monitoramento ao mesmo tempo em que você configura um novo pool de servidores do Skype for Business. (No Skype for Business Server, o monitoramento é habilitado ou desabilitado na base do pool por pool.) Observe que você pode habilitar o monitoramento de um pool sem coletar dados de monitoramento, um processo explicado na seção como configurar a gravação de detalhes da chamada e as configurações de qualidade da experiência desta documentação.

2. Associando um repositório de monitoramento (ou seja, um banco de dados de monitoramento) ao novo pool. Observe que um único repositório pode ser associado a vários pools. Dependendo do número de usuários hospedados em seus pools de registradores, isso significa que não é necessário configurar um banco de dados de monitoramento separado para cada um dos seus pools. Em vez disso, um único repositório de monitoramento pode ser usado por vários pools.

Embora normalmente seja mais fácil habilitar o monitoramento ao mesmo tempo em que o novo pool é criado, também é possível criar um novo pool com o monitoramento desabilitado. Se o fizer, você pode usar o Construtor de Topologias mais tarde para habilitar o serviço: o Construtor de Topologias fornece uma maneira de habilitar ou desabilitar o monitoramento para um pool ou de associar um pool a um repositório de monitoramento diferente. Tenha em mente que embora não exista mais uma função Monitoring Server, ainda será necessário criar um ou mais repositórios de monitoramento: bancos de dados de back-end usados para armazenar os dados reunidos pelo serviço de monitoramento. Esses bancos de dados de back-end podem ser criados usando o Microsoft SQL Server 2008 R2, o Microsoft SQL Server 2012 ou o Microsoft SQL Server 2014.

> [!NOTE]
> Se o monitoramento tiver sido habilitado para um pool, você poderá desabilitar o processo de coleta de dados de monitoramento sem precisar alterar a topologia: o Skype for Business Server oferece uma maneira de desabilitar (e depois habilitar novamente) a CDR (gravação de detalhes de chamadas) ou a qualidade de Experience (QoE) coleta de dados. Para obter mais informações, consulte a seção Como Configurar o Registro de Detalhes das Chamadas e Configurações de Qualidade da Experiência deste documento.

Um outro aprimoramento importante para monitorar o Skype for Business Server é o fato de que os relatórios de monitoramento do Skype for Business Server agora são compatíveis com IPv6: os relatórios que usam o campo endereço IP exibirão endereços IPv4 ou IPv6, dependendo de: 1) a consulta SQL sendo usado; e 2) onde ou não o endereço IPv6 está armazenado no banco de dados de monitoramento.

> [!NOTE]
> Verifique se o Tipo de inicialização do serviço SQL Server Agent é Automático e se o serviço SQL Server Agent está sendo executado para a Instância SQL que está mantendo os bancos de dados de Monitoramento para que os Trabalhos de manutenção do SQL Server de monitoramento padrão possam ser executados com base em seu agendamento sob o controle do Serviço SQL Server Agent.

Esta documentação orienta você pelo processo de instalação e configuração de relatórios de monitoramento e monitoramento para o Skype for Business Server. A documentação fornece instruções passo a passo que o ajudarão a:

- Habilitar o monitoramento na sua topologia e associar um repositório de monitoramento a um Pool de Front-Ends.

- Instale os relatórios de monitoramento do SQL Server Reporting Services e do Skype for Business Server. Relatórios de Monitoramento são relatórios pré-configurados que fornecem visões diferentes das informações armazenadas em um banco de dados de monitoramento.

- Configurar o registro de detalhes das chamadas (CDR) e a coleta de dados de Qualidade da Experiência (QoE). A gravação de detalhes da chamada fornece uma maneira de acompanhar o uso de recursos do Skype for Business Server, como chamadas telefônicas de voz sobre IP (VoIP); mensagens instantâneas (IM); transferências de arquivos; Conferência de áudio/vídeo (A/V); e sessões de compartilhamento de aplicativos. Métricas de QoE acompanham a qualidade de chamadas de áudio e vídeo feitas em sua organização, incluindo itens como o número de pacotes de rede perdidos, ruídos de fundo e o volume de "tremulação" (diferenças no atraso de pacotes).

- Limpar manualmente registros de CDR e/ou QoE do banco de dados de monitoramento.

## <a name="deployment-checklist-for-monitoring"></a>Lista de verificação de implantação para monitoramento

Embora o monitoramento já esteja instalado e ativado em cada servidor front-end, ainda há várias etapas que você deve realizar antes de realmente poder coletar dados de monitoramento para o Skype for Business Server. Essas etapas são descritas na seguinte lista de verificação:

|**Fase**|**Etapas**|**Associação de grupo e função**|**Documentação**|
|:-----|:-----|:-----|:-----|
|**Instalar os pré-requisitos de hardware e software** <br/> |Instale uma versão do Microsoft SQL Server suportada no computador que atuará como armazenamento de dados back-end do monitoramento.  <br/> |Usuário do domínio que também é membro do grupo local de administradores.  <br/> |[Supported Hardware](https://technet.microsoft.com/library/5f9c085d-205e-4235-9061-9ad875283cb0.aspx) <br/> [Server Software and Infrastructure Support](https://technet.microsoft.com/library/4ee5fe38-0191-4710-9aa2-df8895e8c51b.aspx) <br/> |
|**Criar a topologia interna apropriada para dar suporte ao monitoramento** <br/> |Use o construtor de topologia do Skype for Business Server para adicionar bancos de dados de monitoramento à topologia e, em seguida, publicar a topologia atualizada.  <br/> |Para definir uma topologia, um usuário que seja membro do grupo Usuários local.  <br/> Para publicar a topologia, um usuário que seja membro do grupo Administradores de domínio e do grupo RTCUniversalServerAdmins.  <br/> |[Associar um repositório de monitoramento a um pool de front-end no Skype for Business Server](associate-a-monitoring-store.md) <br/> |
|**Habilitar a configuração de monitoramento apropriada** <br/> |Habilite o registro de detalhes das chamadas (CDR) e/ou o monitoramento da Qualidade da Experiência (QoE) no escopo global e/ou local.  <br/> |Um usuário que seja membro do grupo RTCUniversalServerAdmins ou que tenha sido atribuído a uma função RBAC que fornece acesso aos cmdlets CsCdrConfiguration e CsQoEConfiguration.  <br/> |[Configurar a gravação de detalhes da chamada e as configurações de qualidade da experiência no Skype for Business Server](call-detail-recording-and-qoe.md) <br/> |

## <a name="enable-monitoring"></a>Habilitar monitoramento

Embora os agentes de coleta de dados unificados sejam automaticamente instalados e ativados em cada servidor front-end, isso não significa que você começará a coletar dados de monitoramento automaticamente no momento em que você terminar de instalar o Skype for Business Server. Em vez disso, você deve fazer duas coisas: associar seus pools de Front-Ends/Servidores Front-End a um banco de dados de monitoramento, além de habilitar o registro de detalhes das chamadas (CDR) e/ou monitoramento da Qualidade da Experiência (QoE) no escopo global e/ou local.

Para obter instruções passo a passo sobre como associar servidores de front-end ou pools de front-end a um banco de dados de monitoramento, consulte o tópico [associar um repositório de monitoramento a um pool de front-end no Skype for Business Server](associate-a-monitoring-store.md) no guia de implantação. Depois que essas associações tiverem sido feitas e após a publicação da nova topologia do Skype for Business Server, você ainda não poderá coletar os dados de monitoramento. Isso ocorre porque, por padrão, a coleta de dados CDR e QoE é desativada quando você instala o Skype for Business Server.

Para começar a coleta de dados, você precisará habilitar o CDR e/ou o monitoramento QoE. (Observe que você não precisa habilitar o monitoramento de CDR e QoE; se preferir, você pode habilitar um tipo de monitoramento enquanto deixa o outro tipo desabilitado.) Para habilitar o monitoramento de CDR no escopo global, execute o seguinte comando no Shell de gerenciamento do Skype for Business Server:

```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

Você também pode habilitar o monitoramento de CDR no painel de controle do Skype for Business Server. No painel de controle do Skype for Business Server, conclua o seguinte procedimento:

1. Clique em **Monitoramento**.

2. Na guia **Registro de Detalhes das Chamadas**, clique duas vezes na configuração **Global**.

3. No painel **Editar configuração do registro de detalhes das chamadas (CDR)**, selecione **Habilitar monitoramento de CDRs** e clique em **Confirmar**.

Para habilitar o monitoramento de QoE no escopo global, execute este comando no Shell de gerenciamento do Skype for Business Server:

```
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

Se preferir, você também pode habilitar o monitoramento de QoE no painel de controle do Skype for Business Server. No Painel de Controle, execute o seguinte procedimento:

1. Clique em **Monitoramento**.

2. Na guia **Dados da Qualidade da Experiência**, clique duas vezes na configuração **Global**.

3. No painel **Editar configuração da Qualidade da Experiência (QoE)**, selecione **Habilitar monitoramento de dados QoE** e clique em **Confirmar**.

Como observado, os exemplos precedentes habilitam o monitoramento no escopo global; isto é, eles habilitam o monitoramento CDR e QoE em toda a sua organização. Como alternativa, é possível criar definições de configurações CDR e QoE separadas no escopo local e habilitar ou desabilitar seletivamente o monitoramento de cada local. Por exemplo, é possível habilitar o monitoramento CDR para seu local Redmond e desabilitar o monitoramento CDR para Dublin. Para obter mais informações sobre como gerenciar suas configurações de monitoramento, consulte o tópico do guia de implantação [Configurar a gravação de detalhes da chamada e as configurações de qualidade de experiência no Skype for Business Server](call-detail-recording-and-qoe.md).

## <a name="see-also"></a>Confira também

[Planejar o monitoramento no Skype for Business Server](../../plan-your-deployment/monitoring.md)
