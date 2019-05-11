---
title: Excluir definições de configuração de qualidade da experiência no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 'Resumo: Saiba como excluir configurações de Quality of Experience (QoE) no Skype para Business Server.'
ms.openlocfilehash: e177b0870192eba996984e1eb3aae6d520db4661
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926624"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Excluir definições de configuração de qualidade da experiência no Skype para Business Server
 
**Resumo:** Aprenda a excluir definições de qualidade da experiência (QoE) no Skype para Business Server.
  
As métricas de Qualidade da Experiência (QoE) rastreiam a qualidade das chamadas de áudio e vídeo feitas na organização, inclusive o número de pacotes de rede perdidos, o ruído de fundo e a quantidade de tremulação (diferenças no atraso de pacotes). Essas métricas são armazenadas em um banco de dados separado de outros dados (como registros de detalhes das chamadas), permitindo a habilitação e desabilitação da QoE, independente de outros registros de dados.
  
Quando você instala o Skype para Business Server, uma única coleção global de definições de configuração de QoE é criada para você. Os administradores têm a opção de criar coleções de definições personalizadas que podem ser aplicadas a sites individuais. Por design, as configurações no escopo local têm precedência sobre configurações no escopo global. Se você excluir definições no escopo local, a QoE será gerenciada naquele local usando as configurações globais.
  
Observe que você também pode "excluir" as definições globais. No entanto, as definições globais não serão realmente removidas. Em vez disso, todas as propriedades naquele conjunto serão redefinidas de acordo com os valores padrão. Por exemplo, por padrão, a exclusão é habilitada em um conjunto de configurações de QoE. Digamos que você modifique o conjunto global para que a exclusão seja desabilitada. Se você excluir as definições globais mais tarde, todas as propriedades serão redefinidas para seus valores padrão. Neste caso, isso significa que a limpeza será novamente ativada.
  
Você pode remover as definições de configuração de QoE usando o Skype para o painel de controle do Business Server ou usando o cmdlet [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) .
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para excluir as definições de configuração de QoE usando Skype para o painel de controle do servidor de negócios

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte **Delegate Setup Permissions**.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.  
    
3. Na barra de navegação esquerda, clique em **Monitoramento e arquivamento** e em **Dados de qualidade da experiência**.
    
4. Na página **Dados de qualidade da experiência**, clique na política que quiser, clique em **Editar** e em **Excluir**.
    
5. Clique em **OK**.
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Removendo definições de configuração de QoE usando Cmdlets do Windows PowerShell

Você pode excluir as definições de configuração de QoE usando o Windows PowerShell e o cmdlet **Remove-CsQoEConfiguration** . Você pode executar este cmdlet do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo em Skype para Business Server.
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>Para remover um conjunto especificado de definições de configuração de QoE

 Esse comando remove as definições de configuração de QoE aplicadas ao local Redmond:
    
  ```
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>Para remover todas as definições de configuração de QoE aplicadas no escopo local

 Esse comando remove todas as definições de configuração de QoE aplicadas ao escopo local:
    
  ```
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Para remover todas as definições de configuração de QoE onde o monitoramento de QoE foi desabilitado

 Este comando remove todas as definições de configuração de QoE onde o monitoramento de QoE foi desabilitado:
    
  ```
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

Para obter detalhes, consulte [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).
  
## <a name="see-also"></a>Confira também

[Limpar manualmente o registro de detalhes da chamada e bancos de dados de qualidade da experiência no Skype para Business Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

