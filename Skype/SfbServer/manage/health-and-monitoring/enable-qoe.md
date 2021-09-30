---
title: Habilitar a qualidade da experiência no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 'Resumo: saiba como habilitar a QoE (Qualidade da Experiência) em Skype for Business Server.'
ms.openlocfilehash: 3edd7aa136499dcc4b1fd423a1369dcff33f0968
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014745"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a>Habilitar a qualidade da experiência no Skype for Business Server

**Resumo:** saiba como habilitar a QoE (Qualidade da Experiência) no Skype for Business Server.

A QoE (Qualidade da Experiência) registra dados numéricos que indicam a qualidade da mídia e informações sobre participantes, nomes de dispositivo, drivers, endereços IP e tipos de ponto de extremidade envolvidos em chamadas e sessões. Para obter detalhes, consulte [Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring), na documentação de Planejamento.

Use o procedimento a seguir para habilitar QoE para toda sua organização ou para cada site em sua organização.

> [!NOTE]
> Para habilitar o QoE, é necessário primeiro configurar o monitoramento e um back-end de monitoramento. Para obter detalhes, consulte [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a>Para habilitar a QoE usando Skype for Business Server Painel de Controle

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou Skype for Business Server.

2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.

3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e em **Dados da Qualidade da Experiência**.

4. Na página **Dados da Qualidade da Experiência**, clique no conjunto adequado na tabela, clique em **Ação** e em **habilitar QoE**.

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>Habilitando a QoE usando Windows PowerShell Cmdlets

Você pode habilitar a QoE usando Windows PowerShell e o cmdlet **Set-CsQoEConfiguration.** Você pode executar esse cmdlet no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. Para obter detalhes sobre como usar Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). O processo é o mesmo no Skype for Business Server.

### <a name="to-enable-qoe-for-a-single-location"></a>Para habilitar o QoE para um único local

 Para habilitar o QoE, defina o parâmetro EnableQoE para True ($True).

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a>Para desabilitar o QoE para um único local

 Para desabilitar o QoE, defina o parâmetro EnableQoE para False ($False). Isto não desinstala o monitoramento. Pausa o conjunto e armazena os dados do QoE.

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>Para usar um único comando para habilitar o QoE em vários locais

 Este comando habilita o QoE para todas as definições de configuração do QoE atualmente em uso na sua organização.

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

Para obter detalhes, [consulte Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).

## <a name="see-also"></a>Confira também

[Planejamento do monitoramento](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[Implantando o monitoramento](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)