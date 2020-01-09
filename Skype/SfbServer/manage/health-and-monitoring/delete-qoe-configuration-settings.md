---
title: Excluir configurações de qualidade de experiência no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 'Resumo: saiba como excluir as configurações de QoE (qualidade da experiência) no Skype for Business Server.'
ms.openlocfilehash: 134ebe39f41ca051db4ff79eafb094dcc929b5e8
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992418"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Excluir configurações de qualidade de experiência no Skype for Business Server
 
**Resumo:** Saiba como excluir as configurações de QoE (Quality of Experience) no Skype for Business Server.
  
As métricas de Qualidade da Experiência (QoE) rastreiam a qualidade das chamadas de áudio e vídeo feitas na organização, inclusive o número de pacotes de rede perdidos, o ruído de fundo e a quantidade de tremulação (diferenças no atraso de pacotes). Essas métricas são armazenadas em um banco de dados separado de outros dados (como registros de detalhes das chamadas), permitindo a habilitação e desabilitação da QoE, independente de outros registros de dados.
  
Quando você instala o Skype for Business Server, uma única coleção global de definições de configuração de QoE é criada para você. Os administradores têm a opção de criar coleções de definições personalizadas que podem ser aplicadas a sites individuais. Por design, as configurações no escopo local têm precedência sobre configurações no escopo global. Se você excluir definições no escopo local, a QoE será gerenciada naquele local usando as configurações globais.
  
Observe que você também pode "excluir" as configurações globais. No entanto, as definições globais não serão realmente removidas. Em vez disso, todas as propriedades naquele conjunto serão redefinidas de acordo com os valores padrão. Por exemplo, por padrão, a exclusão é habilitada em um conjunto de configurações de QoE. Digamos que você modifique o conjunto global para que a exclusão seja desabilitada. Se você excluir as definições globais mais tarde, todas as propriedades serão redefinidas para seus valores padrão. Neste caso, isso significa que a limpeza será novamente ativada.
  
Você pode remover as definições de configuração de QoE usando o painel de controle do Skype for Business Server ou usando o cmdlet [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) .
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para excluir as configurações de QoE de configuração usando o painel de controle do Skype for Business Server

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte **Delegate Setup Permissions**.
    
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.  
    
3. Na barra de navegação esquerda, clique em **Monitoramento e arquivamento** e em **Dados de qualidade da experiência**.
    
4. Na página **Dados de qualidade da experiência**, clique na política que quiser, clique em **Editar** e em **Excluir**.
    
5. Clique em **OK**.
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Como remover as configurações de QoE usando cmdlets do Windows PowerShell

Você pode excluir as definições de configuração de QoE usando o Windows PowerShell e o cmdlet **Remove-CsQoEConfiguration** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo ["início rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>Para remover um conjunto especificado de definições de configuração de QoE

 Esse comando remove as definições de configuração de QoE aplicadas ao local Redmond:
    
  ```PowerShell
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>Para remover todas as definições de configuração de QoE aplicadas no escopo local

 Esse comando remove todas as definições de configuração de QoE aplicadas ao escopo local:
    
  ```PowerShell
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Para remover todas as definições de configuração de QoE onde o monitoramento de QoE foi desabilitado

 Este comando remove todas as definições de configuração de QoE onde o monitoramento de QoE foi desabilitado:
    
  ```PowerShell
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

Para obter detalhes, consulte [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).
  
## <a name="see-also"></a>Confira também

[Limpar manualmente a gravação de detalhes da chamada e os bancos de dados de qualidade da experiência no Skype for Business Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

