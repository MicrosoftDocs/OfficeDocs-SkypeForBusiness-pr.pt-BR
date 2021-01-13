---
title: Habilitar o registro de detalhes das chamadas no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Resumo: Saiba como habilitar registros cdr (registro de detalhes das chamadas) no Skype for Business Server.'
ms.openlocfilehash: 48d21be6d377df24e859c3ffa6bb8b7858076d29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816881"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a>Habilitar o registro de detalhes das chamadas no Skype for Business Server

**Resumo:** Saiba como habilitar registros cdr (registro de detalhes das chamadas) no Skype for Business Server.

O CDR (registro de detalhes das chamadas) registra informações de uso e diagnóstico sobre atividades ponto a ponto, incluindo mensagens de instância, chamadas VoIP, compartilhamento de aplicativos, transferência de arquivos e reuniões. Os dados de uso podem ser utilizados para calcular o retorno sobre o investimento, enquanto os dados de diagnóstico podem ser usados para solucionar problemas de atividades ponto a ponto e reuniões.

Use o procedimento a seguir para habilitar o CDR para toda a organização ou para cada site da organização.

> [!NOTE]
> Para habilitar o CDR, você deve configurar o monitoramento e um banco de dados de monitoramento. Para obter detalhes, consulte [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a>Para habilitar o CDR com o Painel de Controle do Skype for Business Server

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.

2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.

3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Registro de Detalhes de Chamada**.

4. Na página **Registro de Detalhes das** Chamada, clique no site apropriado na tabela, clique em Ação e em **Habilitar CDR.** 

    > [!NOTE]
    > O CDR é habilitado por padrão.

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>Habilitando o CDR usando cmdlets do Windows PowerShell

Você pode habilitar o CDR usando o Windows PowerShell e o cmdlet **Set-CsCdrConfiguration.** Você pode executar esse cmdlet no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo no Skype for Business Server.

### <a name="to-enable-cdr-for-a-single-location"></a>Para habilitar o CDR para um único local

 Para desabilitar o CDR, de definir o parâmetro EnableCDR como True ($True).

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a>Para desabilitar o CDR para um único local

 Para desabilitar o CDR, de definir o parâmetro EnableCDR como False ($False). Desabilitar o CDR não desinstala o monitoramento. Ele pausa a coleta e o armazenamento de dados de CDR.

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>Para usar um único comando para habilitar o CDR em vários locais

 Este comando habilita o CDR para todas as definições de configuração de CDR em uso na organização.

  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Set-CsCdrConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)

## <a name="see-also"></a>Confira também

[Planejamento do monitoramento](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[Implantando o monitoramento](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
