---
title: Habilite a qualidade de experiência no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 'Resumo: saiba como habilitar a Quality of Experience (QoE) no Skype for Business Server.'
ms.openlocfilehash: 90110c5664e80ac1d4f9d382c20e0fd58d9ce134
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305707"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a>Habilite a qualidade de experiência no Skype for Business Server

**Resumo:** saiba como habilitar a Quality of Experience (QoE) no Skype for Business Server.

A QoE (Qualidade da Experiência) registra dados numéricos que indicam a qualidade da mídia e informações sobre participantes, nomes de dispositivo, drivers, endereços IP e tipos de ponto de extremidade envolvidos em chamadas e sessões. Para obter detalhes, consulte [Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx), na documentação de Planejamento.

Use o procedimento a seguir para habilitar QoE para toda sua organização ou para cada site em sua organização.

> [!NOTE]
> Para habilitar a QoE, é necessário primeiro configurar o monitoramento e um back-end de monitoramento. Para obter detalhes, consulte [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a>Para habilitar a QoE usando o painel de controle do Skype for Business Server

1.  Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Skype for Business Server .

2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.

3. Na barra de navegação esquerda, clique em **Monitoramento e arquivamento** e em **Dados de Qualidade da Experiência**.

4. Na página **Dados de Qualidade da Experiência**, clique no conjunto adequado na tabela, clique em **Ação** e em **Habilitar QoE**.

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>Habilitando a QoE usando cmdlets do Windows PowerShell

Você pode habilitar a QoE usando o Windows PowerShell e o cmdlet **set-CsQoEConfiguration** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo ["início rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo no Skype for Business Server.

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

Para obter detalhes, consulte [set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).

## <a name="see-also"></a>Confira também

[Planejando o monitoramento](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

