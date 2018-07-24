---
title: Habilitar a qualidade da experiência do Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 'Resumo: Saiba como habilitar a qualidade da experiência (QoE) no Skype para Business Server.'
ms.openlocfilehash: 37775223016a463fc7f090f82163fbf8271cd050
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20993198"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a>Habilitar a qualidade da experiência do Skype para Business Server
 
**Resumo:** Aprenda a habilitar a qualidade da experiência (QoE) no Skype para Business Server.
  
A QoE (Qualidade da Experiência) registra dados numéricos que indicam a qualidade da mídia e informações sobre participantes, nomes de dispositivo, drivers, endereços IP e tipos de ponto de extremidade envolvidos em chamadas e sessões. Para obter detalhes, consulte [Planejando o monitoramento](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) na documentação de planejamento.
  
Use o procedimento a seguir para habilitar QoE para toda sua organização ou para cada site em sua organização.
  
> [!NOTE]
> Para habilitar a QoE, é necessário primeiro configurar o monitoramento e um back-end de monitoramento. Para obter detalhes, consulte [Deploying Monitoring](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx). 
  
### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a>Para habilitar o QoE usando Skype para o painel de controle do servidor de negócios

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server .
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.  
    
3. Na barra de navegação esquerda, clique em **Monitoramento e arquivamento** e em **Dados de Qualidade da Experiência**. 
    
4. Na página **Dados de Qualidade da Experiência**, clique no conjunto adequado na tabela, clique em **Ação** e em **Habilitar QoE**.
    
## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>Habilitando o QoE usando Cmdlets do Windows PowerShell

É possível habilitar o QoE usando o Windows PowerShell e o cmdlet **Set-CsQoEConfiguration** . Você pode executar este cmdlet do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo em Skype para Business Server.
  
### <a name="to-enable-qoe-for-a-single-location"></a>Para habilitar a QoE para um único local

 Para habilitar a QoE, defina o parâmetro EnableQoE para True ($True).
    
  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a>Para desabilitar a QoE para um único local

 Para desabilitar a QoE, defina o parâmetro EnableQoE para False ($False). Isso não desinstala o monitoramento; pausa o conjunto e armazena os dados de QoE.
    
  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>Para usar um único comando para habilitar a QoE em vários locais

 Este comando habilita a QoE para todas as definições de configuração de QoE atualmente em uso na sua organização.
    
  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

Para obter detalhes, consulte [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).
  
## <a name="see-also"></a>Consulte também

[Planejamento do monitoramento](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)
  
[Implantando o Monitoring](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

