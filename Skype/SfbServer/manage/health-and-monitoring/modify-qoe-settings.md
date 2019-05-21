---
title: Modificar as configurações de qualidade da experiência no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 'Resumo: saiba como especificar a retenção de dados de QoE no Skype for Business Server.'
ms.openlocfilehash: 89e20b18aa285bd4ee61df12c822e487dd6b37a4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280002"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a>Modificar as configurações de qualidade da experiência no Skype for Business Server

**Resumo:** Saiba como especificar a retenção de dados de QoE no Skype for Business Server.

Por padrão, os dados de QoE (Qualidade de Experiência) são limpos após 60 dias. Você pode usar as configurações da página **Dados de Qualidade de Experiência** para manter os dados por um período maior ou menor. Se você desabilitar a QoE, os dados capturados antes da habilitação da QoE também ficarão sujeitos à limpeza.

> [!NOTE]
> Você deve configurar o registro de detalhes de chamadas (CDR) e a QoE para manter dados durante o mesmo número de dias. Cada chamada nos relatórios de detalhes de chamadas (CDRs), disponíveis na página inicial de relatórios do Monitoring Reports, inclui informações de CDR e QoE. Se o momento da limpeza para o CDR e a QoE for diferente, algumas chamadas podem incluir somente dados de CDR, enquanto outros podem incluir somente dados de QoE.

O procedimento a seguir descreve como definir as configurações de limpeza para dados de QoE.

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>Para especificar a retenção de dados de QoE usando o painel de controle do Skype for Business Server

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte **Delegate Setup Permissions**.

2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.

3. Na barra de navegação esquerda, clique em **Monitoramento e arquivamento** e em **Dados de Qualidade da Experiência**.

4. Na página **Dados de Qualidade de Experiência**, clique no site adequado na tabela, clique em **Editar** e em **Exibir Detalhes**.

5. Para ativar a limpeza, selecione **Habilitar a Limpeza do QoE**.

6. Em **Manter QoE por um período máximo de (dias)**, selecione o número máximo de dias durante os quais dados de QoE devem ser mantidos.

7. Clique em **Confirmar**.

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>Especificando a retenção de QoE usando cmdlets do Windows PowerShell

Você pode criar configurações de retenção de QoE usando o Windows PowerShell e o cmdlet **set-CsQoEConfiguration** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo ["início rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo no Skype for Business Server.

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

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) .

## <a name="see-also"></a>Confira também

[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
