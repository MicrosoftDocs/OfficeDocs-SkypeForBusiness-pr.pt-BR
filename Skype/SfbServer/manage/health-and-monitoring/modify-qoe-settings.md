---
title: Modificar as configurações de qualidade da experiência no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 'Resumo: Saiba como especificar a retenção de dados de QoE em Skype para Business Server.'
ms.openlocfilehash: a456a2528b78242849f651209e70c98046ebe0c3
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21012663"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a>Modificar as configurações de qualidade da experiência no Skype para Business Server
 
**Resumo:** Saiba como especificar a retenção de dados de QoE em Skype para Business Server.
  
Por padrão, os dados de QoE (Qualidade de Experiência) são limpos após 60 dias. Você pode usar as configurações da página **Dados de Qualidade de Experiência** para manter os dados por um período maior ou menor. Se você desabilitar a QoE, os dados capturados antes da habilitação da QoE também ficarão sujeitos à limpeza.
  
> [!NOTE]
> Você deve configurar o registro de detalhes de chamadas (CDR) e a QoE para manter dados durante o mesmo número de dias. Cada chamada nos relatórios de detalhes de chamadas (CDRs), disponíveis na página inicial de relatórios do Monitoring Reports, inclui informações de CDR e QoE. Se o momento da limpeza para o CDR e a QoE for diferente, algumas chamadas podem incluir somente dados de CDR, enquanto outros podem incluir somente dados de QoE. 
  
O procedimento a seguir descreve como definir as configurações de limpeza para dados de QoE. 
  
### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>Para especificar a retenção de dados de QoE usando Skype para o painel de controle do servidor de negócios

1.  Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte **Delegate Setup Permissions**.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.  
    
3. Na barra de navegação esquerda, clique em **Monitoramento e arquivamento** e em **Dados de Qualidade da Experiência**.
    
4. Na página **Dados de Qualidade de Experiência**, clique no site adequado na tabela, clique em **Editar** e em **Exibir Detalhes**.
    
5. Para ativar a limpeza, selecione **Habilitar a Limpeza do QoE**.
    
6. Em **Manter QoE por um período máximo de (dias)**, selecione o número máximo de dias durante os quais dados de QoE devem ser mantidos.
    
7. Clique em **Confirmar**.
    
## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>Especificar a retenção de QoE usando Cmdlets do Windows PowerShell

Você pode criar configurações de retenção de QoE usando o Windows PowerShell e o cmdlet **Set-CsQoEConfiguration** . Você pode executar este cmdlet do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo em Skype para Business Server.
  
### <a name="to-specify-qoe-retention-for-a-specific-location"></a>Para especificar a retenção de QoE de um local específico

- Esse comando permite limpar os dados de QoE do site da Redmond e configura o site para manter os dados de QoE por 20 dias.
    
  ```
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a>Para especificar a retenção de QoE de vários locais

- Esse comando configura a retenção de QoE para todos as configurações de QoE em uso em uma organização.
    
  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20 
  ```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) .
  
## <a name="see-also"></a>Consulte também

[Implantando o Monitoring](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)