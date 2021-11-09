---
title: Excluir configurações de Qualidade de Experiência no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 'Resumo: saiba como excluir as configurações de Qualidade da Experiência (QoE) no Skype for Business Server.'
ms.openlocfilehash: 96c6f15903a3e7cdc4305c6c90faddf0ee8ff743
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854305"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Excluir configurações de Qualidade de Experiência no Skype for Business Server
 
**Resumo:** Saiba como excluir as configurações de QoE (Qualidade da Experiência) no Skype for Business Server.
  
Os atributos métricos da Qualidade da Experiência (QoE) rastreiam a qualidade das chamadas de áudio e vídeo feitas na organização, inclusive o número de pacotes de rede perdidos, o ruído de fundo e a quantidade de "jitter" (diferenças no atraso de pacotes). Esses atributos métricos são armazenados em um banco de dados separado de outros dados (como registros de detalhes das chamadas), permitindo a habilitação e desabilitação do QoE, independentemente de outros registros de dados.
  
Quando você instala Skype for Business Server, uma única coleção global de configurações de QoE é criada para você. Os administradores também têm a opção de criar conjuntos personalizados de definições que podem ser aplicados a sites individuais. Por design, as configurações no escopo do site têm precedência sobre configurações no escopo global. Se você excluir definições no escopo do site, o QoE será gerenciado naquele site usando as configurações globais.
  
Observe que você também pode "excluir" as configurações globais. Contudo, elas não serão realmente removidas. Em vez disso, todas as propriedades naquele conjunto serão redefinidas de acordo com os valores padrão. Por exemplo, por padrão, a exclusão é habilitada em um conjunto de configurações de QoE. Digamos que você modifique o conjunto global para que a exclusão seja desabilitada. Se depois você resolver apagar as definições globais, todas as propriedades serão redefinidas para os valores padrão. Nesse caso, isso significa que a exclusão será habilitada novamente.
  
Você pode remover as configurações de QoE usando o Painel de Controle Skype for Business Server ou usando o cmdlet [Remove-CsQoEConfiguration.](/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para excluir as configurações de QoE usando Skype for Business Server Painel de Controle

1.  Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte **Delegate Setup Permissions**.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.  
    
3. Na barra de navegação esquerda, clique em **Monitoramento e arquivamento** e em **Dados de Qualidade da Experiência**.
    
4. Na página **Dados de Qualidade de Experiência**, clique na política que quiser, clique em **Editar** e em **Excluir**.
    
5. Clique em **OK**.
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Removendo a configuração de QoE Configurações usando Windows PowerShell cmdlets

Você pode excluir as configurações de QoE usando Windows PowerShell e o cmdlet **Remove-CsQoEConfiguration.** Você pode executar esse cmdlet no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. Para obter detalhes sobre como usar Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>Para remover um conjunto especificado de definições de configuração de QoE

 Esse comando remove as definições de configuração de QoE aplicadas ao site de Redmond:
    
  ```PowerShell
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>Para remover todas as definições de configuração de QoE aplicadas no escopo do site

 Esse comando remove todas as definições de configuração de QoE aplicadas ao escopo do site:
    
  ```PowerShell
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Para remover todas as definições de configuração de QoE onde o monitoramento de QoE for desabilitado

 Este comando remove todas as definições de configuração de QoE onde o monitoramento de QoE foi desabilitado:
    
  ```PowerShell
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

Para obter detalhes, [consulte Remove-CsQoEConfiguration](/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).
  
## <a name="see-also"></a>Confira também

[Limpar manualmente o registro de detalhes de chamada e os bancos de dados de Qualidade da Experiência no Skype for Business Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)