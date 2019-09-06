---
title: Habilitar a gravação de detalhes da chamada no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Resumo: saiba como habilitar registros CDR (registro de detalhes de chamadas) no Skype for Business Server.'
ms.openlocfilehash: 015ac3b57420401894e82c267e9737990ca7affb
ms.sourcegitcommit: 332817f49ec1e6767334fdd4c2ec3f791020a26c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/05/2019
ms.locfileid: "36767053"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a>Habilitar a gravação de detalhes da chamada no Skype for Business Server

**Resumo:** Saiba como habilitar registros CDR (registro de detalhes de chamadas) no Skype for Business Server.

O CDR (registro de detalhes das chamadas) registra informações de utilização e diagnóstico sobre atividades ponto a ponto, incluindo serviço de mensagens instantâneas, chamadas do protocolo VoIP, compartilhamento de aplicativos, transferência de arquivos e reuniões. Os dados de uso podem ser utilizados para calcular o ROI (retorno sobre o investimento), enquanto os dados de diagnóstico podem ser usados para solucionar problemas de atividades ponto a ponto e reuniões.

Use o procedimento a seguir para ativar o CDR para a organização inteira ou para cada local da organização.

> [!NOTE]
> Para habilitar o CDR, é preciso configurar o monitoramento e o banco de dados de monitoramento. Para obter detalhes, consulte [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a>Para habilitar CDR com o painel de controle do Skype for Business Server

1.  Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Skype for Business Server .

2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.

3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Registro de Detalhes das Chamadas**.

4. Na página **Registro de Detalhes das Chamadas**, clique no local apropriado na tabela, em **Ação** e em **Habilitar CDR**.

    > [!NOTE]
    > O CDR é ativado por padrão.

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>Como habilitar o CDR usando cmdlets do Windows PowerShell

Você pode habilitar o CDR usando o Windows PowerShell e o cmdlet **set-CsCdrConfiguration** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo ["início rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo no Skype for Business Server.

### <a name="to-enable-cdr-for-a-single-location"></a>Para habilitar o CDR para um único local

 Para desabilitar o CDR, defina o parâmetro EnableCDR como Verdadeiro ($True).

  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a>Para desabilitar o CDR para um único local

 Para desabilitar o CDR, defina o parâmetro EnableCDR como Falso ($False). Desabilitar o CDR não desinstalará o monitoramento, apenas pausará a coleta e o armazenamento de dados de CDR.

  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>Para usar um único comando para habilitar o CDR em vários locais

 Este comando habilita o CDR para todas as configurações do CDR em uso na sua organização.

  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .

## <a name="see-also"></a>Confira também

[Planejando o monitoramento](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
