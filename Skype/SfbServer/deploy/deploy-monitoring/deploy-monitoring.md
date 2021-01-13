---
title: Implantar monitoramento no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: 'Resumo: saiba como implantar o monitoramento no Skype for Business Server.'
ms.openlocfilehash: 89474b7d40a63911c6a79bee719573516a9d423a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802271"
---
# <a name="deploy-monitoring-in-skype-for-business-server"></a>Implantar monitoramento no Skype for Business Server

**Resumo:** Saiba como implantar o monitoramento no Skype for Business Server.

Antes de executar essas tarefas, revise [o plano de monitoramento no Skype for Business Server.](../../plan-your-deployment/monitoring.md)

Normalmente, você implementará serviços de monitoramento em sua topologia concluindo as duas etapas a seguir:

1. Habilitando o monitoramento ao mesmo tempo em que você configura um novo pool do Skype for Business Server. (No Skype for Business Server, o monitoramento está habilitado ou desabilitado em uma base pool por pool.) Observe que você pode habilitar o monitoramento de um pool sem realmente coletar dados de monitoramento, um processo explicado na seção Definindo o Registro de Detalhes das Chamada e as Configurações de Qualidade da Experiência desta documentação.

2. Associando um repositório de monitoramento (ou seja, um banco de dados de monitoramento) ao novo pool. Observe que um único repositório pode ser associado a vários pools. Dependendo do número de usuários hospedados em seus pools de registradores, isso significa que não é necessário configurar um banco de dados de monitoramento separado para cada um dos seus pools. Em vez disso, um único repositório de monitoramento pode ser usado por vários pools.

Embora normalmente seja mais fácil habilitar o monitoramento ao mesmo tempo em que o novo pool é criado, também é possível criar um novo pool com o monitoramento desabilitado. Se o fizer, você pode usar o Construtor de Topologias mais tarde para habilitar o serviço: o Construtor de Topologias fornece uma maneira de habilitar ou desabilitar o monitoramento para um pool ou de associar um pool a um repositório de monitoramento diferente. Tenha em mente que, embora não haja mais uma função de Monitoring Server, você ainda precisará criar um ou mais armazenamentos de monitoramento: bancos de dados back-end usados para armazenar os dados coletados pelo serviço de monitoramento. Esses bancos de dados back-end podem ser criados usando o Microsoft SQL Server 2008 R2, Microsoft SQL Server 2012, Microsoft SQL Server 2014 ou Microsoft SQL Server 2019.

> [!NOTE]
> Se o monitoramento tiver sido habilitado para um pool, você poderá desabilitar o processo de coleta de dados de monitoramento sem precisar alterar sua topologia: o Skype for Business Server oferece uma maneira de desabilitar (e reabilitar posteriormente) o Registro de Detalhes das Chamadas (CDR) ou a coleta de dados de Qualidade da Experiência (QoE). Para mais informações, consulte a seção Como Configurar o Registro de Detalhes de Chamadas e Configurações de Qualidade de Experiência deste documento.

Outro aprimoramento importante para o monitoramento no Skype for Business Server é o fato de que os Relatórios de Monitoramento do Skype for Business Server agora suportam IPv6: os relatórios que usam o campo Endereço IP exibirão endereços IPv4 ou IPv6 dependendo de: 1) a consulta SQL que está sendo usada; e, 2) onde ou não o endereço IPv6 está armazenado no banco de dados de monitoramento.

> [!NOTE]
> Certifique-se de que o Tipo de Inicialização do Serviço do SQL Server Agent seja Automático e que o Serviço do SQL Server Agent está em execução para a Instância do SQL que está segurando os bancos de dados de Monitoramento, para que os Trabalhos de Manutenção do SQL Server de Monitoramento Padrão possam ser executados com base no agendamento sob o controle do SERVIÇO do SQL Server Agent.

Esta documentação o orienta durante o processo de instalação e configuração de monitoramento e relatórios de monitoramento para o Skype for Business Server. A documentação fornece instruções passo a passo que o ajudarão a:

- Habilitar o monitoramento na sua topologia e associar um repositório de monitoramento a um pool de Front End.

- Instale o SQL Server Reporting Services e os Relatórios de Monitoramento do Skype for Business Server. Relatórios de Monitoramento são relatórios pré-configurados que fornecem visões diferentes das informações armazenadas em um banco de dados de monitoramento.

- Configure o registro de detalhes das chamada (CDR) e a coleta de dados de Qualidade da Experiência (QoE). O registro de detalhes das chamadas oferece uma maneira de rastrear o uso de recursos do Skype for Business Server, como chamadas telefônicas VoIP; mensagens instantâneas (IM); transferências de arquivos; conferência de áudio/vídeo (A/V); e sessões de compartilhamento de aplicativos. Métricas de QoE rastreiam a qualidade de chamadas de áudio/vídeo feitas em sua organização, incluindo itens como o número de pacotes de rede perdidos, ruídos de fundo e o volume de "tremulação" (diferenças no intervalo de pacotes).

- Limpar manualmente registros de CDR e/ou QoE do banco de dados de monitoramento.

## <a name="deployment-checklist-for-monitoring"></a>Lista de verificação de implantação para monitoramento

Embora o monitoramento já esteja instalado e ativado em cada servidor front-end, ainda há várias etapas que você deve realizar antes de poder coletar dados de monitoramento do Skype for Business Server. Essas etapas são descritas na seguinte lista de verificação:

|**Fase**|**Etapas**|**Função e associação de grupo**|**Documentação**|
|:-----|:-----|:-----|:-----|
|**Instale o pré-requisito de hardware e software** <br/> |Instale uma versão do Microsoft SQL Server suportada no computador que atuará como armazenamento de dados backend do monitoramento.  <br/> |Usuário do domínio que também é membro do grupo local de administradores.  <br/> |[Hardware suportado](https://technet.microsoft.com/library/5f9c085d-205e-4235-9061-9ad875283cb0.aspx) <br/> [Suporte de infraestrutura e software do servidor](https://technet.microsoft.com/library/4ee5fe38-0191-4710-9aa2-df8895e8c51b.aspx) <br/> |
|**Criar a topologia interna apropriada para dar suporte ao monitoramento** <br/> |Use o Construtor de Topologias do Skype for Business Server para adicionar bancos de dados de monitoramento à topologia e publicou a topologia atualizada.  <br/> |Para definir uma topologia, um usuário que seja membro do grupo local de usuários.  <br/> Para publicar a topologia, um usuário que seja membro do grupo de administradores de domínio e do grupo RTCUniversalServerAdmins.  <br/> |[Associar um armazenamento de monitoramento a um pool de Front-End no Skype for Business Server](associate-a-monitoring-store.md) <br/> |
|**Habilitar a configuração de monitoramento apropriada** <br/> |Habilitar o registro de detalhes das chamada (CDR) e/ou monitoramento de QoE (Qualidade da Experiência) nos escopos global e/ou de site.  <br/> |Um usuário que seja membro do grupo RTCUniversalServerAdmins ou que tenha sido atribuído a uma função RBAC que fornece acesso aos cmdlets CsCdrConfiguration e CsQoEConfiguration .  <br/> |[Definir o registro de detalhes das chamadas e as configurações de Qualidade da Experiência no Skype for Business Server](call-detail-recording-and-qoe.md) <br/> |

## <a name="enable-monitoring"></a>Habilitar monitoramento

Embora os agentes de coleta de dados unificados sejam instalados e ativados automaticamente em cada servidor front-end, isso não significa que você começará automaticamente a coletar dados de monitoramento no momento em que terminar de instalar o Skype for Business Server. Em vez disso, você deve fazer duas coisas: você deve associar seus pools de servidores front-end/front-end a um banco de dados de monitoramento e deve habilitar o registro de detalhes das chamada (CDR) e/ou monitoramento de QoE (Qualidade da Experiência) no escopo global e/ou no escopo do site.

Para obter instruções passo a passo sobre como associar servidores front-end ou pools de front-end a um banco de dados de monitoramento, consulte o tópico [Associate a monitoring store with a Front End pool in Skype for Business Server](associate-a-monitoring-store.md) in the Deployment guide. Após essas associações serem feitas e após sua nova topologia do Skype for Business Server ter sido publicada, você ainda não poderá coletar dados de monitoramento. Isso acontece porque, por padrão, a coleta de dados CDR e QoE é desabilitada quando você instala o Skype for Business Server.

Para poder começar a coletar dados necessários habilite o CDR e/ou monitoramento QoE. (Observe que você não precisa habilitar o CDR e o monitoramento QoE; se preferir, pode habilitar um tipo de monitoramento deixando o outro tipo desabilitado.) Para habilitar o monitoramento CDR no escopo global, execute o seguinte comando no Shell de Gerenciamento do Skype for Business Server:

```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

Como alternativa, você pode habilitar o monitoramento CDR no Painel de Controle do Skype for Business Server. No Painel de Controle do Skype for Business Server, conclua o seguinte procedimento:

1. Clique em **Monitoramento**.

2. Na guia **Registro de Detalhes da Chamada**, clique duas vezes na configuração **Global**.

3. No painel **Editar configuração do registro de detalhe da chamada (CDR)**, selecione **Habilitar monitoramento de CDRs** e clique em **Confirmar**.

Para habilitar o monitoramento de QoE no escopo global, execute este comando no Shell de Gerenciamento do Skype for Business Server:

```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

Se preferir, você também pode habilitar o monitoramento QoE no Painel de Controle do Skype for Business Server. No Painel de Controle, conclua o seguinte procedimento:

1. Clique em **Monitoramento**.

2. Na guia **Dados da Qualidade da Experiência**, clique duas vezes na configuração **Global**.

3. No painel **Editar configuração da Qualidade da Experiência (QoE)**, selecione **Habilitar monitoramento de dados QoE** e clique em **Confirmar**.

Como observado, os exemplos anteriores habilitam o monitoramento no escopo global; isto é, eles habilitam o monitoramento CDR e QoE através da sua organização. Em alternativa, é possível criar definições de configurações CDR e QoE separadas no escopo local e habilitar ou desabilitar seletivamente o monitoramento de cada local. Por exemplo, é possível habilitar o monitoramento CDR para seu local Redmond, desabilitar o monitoramento CDR para Dublin. Para obter mais informações sobre como gerenciar suas definições de configuração de monitoramento, consulte o tópico do guia de implantação Configurar o registro de detalhes das chamadas e as configurações de Qualidade da Experiência no [Skype for Business Server.](call-detail-recording-and-qoe.md)

## <a name="see-also"></a>Confira também

[Planejar o monitoramento no Skype for Business Server](../../plan-your-deployment/monitoring.md)
