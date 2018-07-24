---
title: Implantar o monitoramento no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: 'Resumo: Saiba como implantar o monitoramento no Skype para Business Server.'
ms.openlocfilehash: 4a2105e99b37574b3622c3d8bbb4cb2c05ecb71d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20989994"
---
# <a name="deploy-monitoring-in-skype-for-business-server"></a>Implantar o monitoramento no Skype para Business Server
 
**Resumo:** Aprenda a implantar o monitoramento no Skype para Business Server.
 
Antes de executar essas tarefas, revise [Plan for monitoring no Skype para Business Server](../../plan-your-deployment/monitoring.md).
 
Geralmente, você implementará serviços de monitoramento em sua topologia concluindo as duas etapas a seguir:
  
1. Habilitar monitoramento ao mesmo tempo configurar um novo Skype para pool de servidores de negócios. (No Skype para Business Server, monitoring é ativado ou desativado em uma base de pool por pool.) Observe que você pode habilitar o monitoramento para um pool sem realmente coleta de dados de monitoramento, um processo explicado na seção Configuração do Call Detail Recording and Quality of Experience Settings desta documentação.
    
2. Associando um repositório de monitoramento (ou seja, um banco de dados de monitoramento) ao novo pool. Observe que um único repositório pode ser associado a vários pools. Dependendo do número de usuários hospedados em seus pools de registradores, isso significa que não é necessário configurar um banco de dados de monitoramento separado para cada um dos seus pools. Em vez disso, um único repositório de monitoramento pode ser usado por vários pools.
    
Embora normalmente seja mais fácil habilitar o monitoramento ao mesmo tempo em que o novo pool é criado, também é possível criar um novo pool com o monitoramento desabilitado. Se o fizer, você pode usar o Construtor de Topologias mais tarde para habilitar o serviço: o Construtor de Topologias fornece uma maneira de habilitar ou desabilitar o monitoramento para um pool ou de associar um pool a um repositório de monitoramento diferente. Tenha em mente que embora não exista mais uma função Monitoring Server, ainda será necessário criar um ou mais repositórios de monitoramento: bancos de dados de back-end usados para armazenar os dados reunidos pelo serviço de monitoramento. Esses bancos de dados de back-end podem ser criados usando o Microsoft SQL Server 2008 R2, o Microsoft SQL Server 2012 ou o Microsoft SQL Server 2014.
  
> [!NOTE]
> Se monitoring tiver sido habilitado para um pool, você pode desabilitar o processo de coleta de dados de monitoramento sem precisar alterar sua topologia: Skype para Business Server oferece uma maneira de desabilitar (e mais tarde reabilitar) gravação de detalhes das chamadas (CDR) ou a qualidade das Coleta de dados de experiência (QoE). Para obter mais informações, consulte a seção Como Configurar o Registro de Detalhes das Chamadas e Configurações de Qualidade da Experiência deste documento. 
  
Uma das outra melhorias importante ao monitoramento no Skype para Business Server é o fato de que Skype para relatórios de monitoramento de servidor de negócios agora oferece suporte a IPv6: relatórios que usam o campo de endereço IP exibirá em IPv4 ou IPv6 endereços dependendo da: 1) a consulta SQL está sendo usado; e, 2) onde ou não o endereço IPv6 é armazenado no banco de dados de monitoramento.
  
> [!NOTE]
> Verifique se o Tipo de inicialização do serviço SQL Server Agent é Automático e se o serviço SQL Server Agent está sendo executado para a Instância SQL que está mantendo os bancos de dados de Monitoramento para que os Trabalhos de manutenção do SQL Server de monitoramento padrão possam ser executados com base em seu agendamento sob o controle do Serviço SQL Server Agent. 
  
Esta documentação o orienta durante o processo de instalar e configurar os relatórios de monitoramento e monitoramento para Skype para Business Server. A documentação fornece instruções passo a passo que o ajudarão a:
  
- Habilitar o monitoramento na sua topologia e associar um repositório de monitoramento a um Pool de Front-Ends.
    
- Instale o SQL Server Reporting Services e o Skype para relatórios de monitoramento de servidor de negócios. Relatórios de Monitoramento são relatórios pré-configurados que fornecem visões diferentes das informações armazenadas em um banco de dados de monitoramento.
    
- Configurar o registro de detalhes das chamadas (CDR) e a coleta de dados de Qualidade da Experiência (QoE). Registro de detalhes da chamada fornece uma maneira de controlar o uso do Skype para recursos de Business Server, como voz sobre IP (VoIP) de telefonemas; mensagens instantâneas (IM); transferências de arquivos; áudio/vídeo (A / V) conferência; e sessões de compartilhamento de aplicativo. Métricas de QoE acompanham a qualidade de chamadas de áudio e vídeo feitas em sua organização, incluindo itens como o número de pacotes de rede perdidos, ruídos de fundo e o volume de "tremulação" (diferenças no atraso de pacotes).
    
- Limpar manualmente registros de CDR e/ou QoE do banco de dados de monitoramento.
    
## <a name="deployment-checklist-for-monitoring"></a>Lista de verificação de implantação para monitoramento

Embora o monitoramento já está instalada e ativada em cada servidor Front-End, ainda há diversas etapas que você deve realizar antes de você poder realmente sendo coletar dados de monitoramento para Skype para Business Server. Essas etapas são descritas na seguinte lista de verificação:
  
|**Fase**|**Etapas**|**Associação de grupo e função**|**Documentação**|
|:-----|:-----|:-----|:-----|
|**Instalar os pré-requisitos de hardware e software** <br/> |Instale uma versão do Microsoft SQL Server suportada no computador que atuará como armazenamento de dados back-end do monitoramento.  <br/> |Usuário do domínio que também é membro do grupo local de administradores.  <br/> |[Hardware suportado](http://technet.microsoft.com/library/5f9c085d-205e-4235-9061-9ad875283cb0.aspx) <br/> [Server Software and Infrastructure Support](http://technet.microsoft.com/library/4ee5fe38-0191-4710-9aa2-df8895e8c51b.aspx) <br/> |
|**Criar a topologia interna apropriada para dar suporte ao monitoramento** <br/> |Skype de uso para o construtor de topologia de servidor de negócios adicionar à topologia, bancos de dados de monitoramento, em seguida, publique a topologia atualizada.  <br/> |Para definir uma topologia, um usuário que seja membro do grupo Usuários local.  <br/> Para publicar a topologia, um usuário que seja membro do grupo Administradores de domínio e do grupo RTCUniversalServerAdmins.  <br/> |[Associar um repositório de monitoramento um pool de Front-End no Skype para Business Server](associate-a-monitoring-store.md) <br/> |
|**Habilitar a configuração de monitoramento apropriada** <br/> |Habilite o registro de detalhes das chamadas (CDR) e/ou o monitoramento da Qualidade da Experiência (QoE) no escopo global e/ou local.  <br/> |Um usuário que seja membro do grupo RTCUniversalServerAdmins ou que tenha sido atribuído a uma função RBAC que fornece acesso aos cmdlets CsCdrConfiguration e CsQoEConfiguration.  <br/> |[Configurar o registro de detalhes de chamada e configurações de qualidade da experiência no Skype para Business Server](call-detail-recording-and-qoe.md) <br/> |
   
## <a name="enable-monitoring"></a>Habilitar monitoramento

Embora os agentes de coleta de dados unificado são automaticamente instalados e ativados em cada servidor Front-End, que não significa que você passará automaticamente a coletar dados de monitoramento no momento em que você concluir a instalação Skype para Business Server. Em vez disso, você deve fazer duas coisas: associar seus pools de Front-Ends/Servidores Front-End a um banco de dados de monitoramento, além de habilitar o registro de detalhes das chamadas (CDR) e/ou monitoramento da Qualidade da Experiência (QoE) no escopo global e/ou local.
  
Para obter instruções passo a passo sobre como associar pools de Front-End ou servidores Front-End um banco de dados de monitoramento, consulte o tópico [associar um repositório de monitoramento com um pool de Front-End no Skype para Business Server](associate-a-monitoring-store.md) no guia de implantação. Depois que essas associações foram feitas e, depois que tiver sido publicado seu novo Skype para topologia de servidores corporativos, ainda não será capaz de coletar dados de monitoramento. Isso acontece porque, por padrão, a coleta de dados de CDR e QoE for desabilitada quando você instala o Skype para Business Server.
  
Para começar a coleta de dados, você precisará habilitar o CDR e/ou o monitoramento QoE. (Observe que você não tiver habilitado a ambos os CDR e QoE monitoring; se você preferir, é possível habilitar um tipo de monitoramento, deixando o outro tipo desabilitado). Para habilitar o CDR monitorando em executar o escopo global o seguinte comando dentro do Skype do Shell de gerenciamento do servidor de negócios:
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

Como alternativa, é possível habilitar o CDR monitoramento de dentro do Skype para painel de controle do servidor de negócios. De dentro do Skype para painel de controle do servidor de negócios, conclua o procedimento a seguir:
  
1. Clique em **Monitoramento**.
    
2. Na guia **Registro de Detalhes das Chamadas**, clique duas vezes na configuração **Global**.
    
3. No painel **Editar configuração do registro de detalhes das chamadas (CDR)**, selecione **Habilitar monitoramento de CDRs** e clique em **Confirmar**.
    
Para habilitar o QoE monitoring no escopo global, execute este comando a partir do Skype do Shell de gerenciamento do servidor de negócios:
  
```
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

Se você preferir, você também pode habilitar o QoE monitoring de dentro do Skype para painel de controle do servidor de negócios. No Painel de Controle, execute o seguinte procedimento:
  
1. Clique em **Monitoramento**.
    
2. Na guia **Dados da Qualidade da Experiência**, clique duas vezes na configuração **Global**.
    
3. No painel **Editar configuração da Qualidade da Experiência (QoE)**, selecione **Habilitar monitoramento de dados QoE** e clique em **Confirmar**.
    
Como observado, os exemplos precedentes habilitam o monitoramento no escopo global; isto é, eles habilitam o monitoramento CDR e QoE em toda a sua organização. Como alternativa, é possível criar definições de configurações CDR e QoE separadas no escopo local e habilitar ou desabilitar seletivamente o monitoramento de cada local. Por exemplo, é possível habilitar o monitoramento CDR para seu local Redmond e desabilitar o monitoramento CDR para Dublin. Para obter mais informações sobre como gerenciar suas definições de configuração de monitoramento, consulte o tópico do guia de implantação [Configure chamada gravação de detalhes e configurações de qualidade da experiência no Skype para Business Server](call-detail-recording-and-qoe.md).
  
## <a name="see-also"></a>Consulte também

[Plano para monitoramento no Skype para Business Server](../../plan-your-deployment/monitoring.md)