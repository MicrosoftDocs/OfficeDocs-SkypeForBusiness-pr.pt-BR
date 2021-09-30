---
title: Modificar configurações de Qualidade de Experiência no Skype for Business Server
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
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 'Resumo: saiba como especificar a retenção de dados QoE no Skype for Business Server.'
ms.openlocfilehash: c8480b5deb8007c050968c399ee20eb14755e6ba
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013945"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a>Modificar configurações de Qualidade de Experiência no Skype for Business Server

**Resumo:** Saiba como especificar a retenção de dados QoE no Skype for Business Server.

Por padrão, os dados de QoE (Qualidade de Experiência) são limpos após 60 dias. Você pode usar as configurações da página **Dados de Qualidade de Experiência** para manter os dados por um período maior ou menor. Se você desabilitar a QoE, os dados capturados antes da habilitação da QoE também ficarão sujeitos à limpeza.

> [!NOTE]
> Você deve configurar o registro de detalhes de chamadas (CDR) e a QoE para manter dados durante o mesmo número de dias. Cada chamada nos relatórios de detalhes de chamadas (CDRs), disponíveis na página inicial de relatórios do Monitoring Reports, inclui informações de CDR e QoE. Se o momento da limpeza para o CDR e a QoE for diferente, algumas chamadas podem incluir somente dados de CDR, enquanto outros podem incluir somente dados de QoE.

O procedimento a seguir descreve como definir as configurações de limpeza para dados de QoE.

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>Para especificar a retenção de dados QoE usando Skype for Business Server Painel de Controle

1.  Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte **Delegate Setup Permissions**.

2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.

3. Na barra de navegação à esquerda, clique em **Monitoramento e Arquivamento** e clique em **Dados de Qualidade de Experiência**.

4. Na página **Dados de Qualidade de Experiência**, clique no site adequado na tabela, clique em **Editar** e em **Exibir Detalhes**.

5. Para ativar a limpeza, selecione **Habilitar a Limpeza do QoE**.

6. Em **Manter QoE por um período máximo de (dias)** selecione o número máximo de dias durante os quais dados de QoE devem ser mantidos.


7. Clique em **Confirmar**.

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>Especificando a retenção de QoE usando Windows PowerShell Cmdlets

Você pode criar configurações de retenção de QoE usando Windows PowerShell e o cmdlet **Set-CsQoEConfiguration.** Você pode executar esse cmdlet no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. Para obter detalhes sobre como usar Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). O processo é o mesmo no Skype for Business Server.

### <a name="to-specify-qoe-retention-for-a-specific-location"></a>Para especificar a retenção de QoE de um local específico

- Esse comando permite limpar os dados de QoE do site da Redmond e configura o site para manter os dados de QoE por 20 dias.

  ```PowerShell
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a>Para especificar a retenção de QoE de vários locais

- Esse comando configura a retenção de QoE para todos as configurações de QoE em uso em uma organização.

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

Para obter mais informações, consulte o tópico de ajuda do cmdlet [Set-CsQoEConfiguration.](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)

## <a name="see-also"></a>Confira também

[Implantando o monitoramento](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)