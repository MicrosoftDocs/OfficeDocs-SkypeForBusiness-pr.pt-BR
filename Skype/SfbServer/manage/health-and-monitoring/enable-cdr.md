---
title: Habilitar o registro de detalhes de chamada Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Resumo: saiba como habilitar registros de registro de detalhes de chamada (CDR) no Skype for Business Server.'
ms.openlocfilehash: bb041b82a32c4e3c03a62faf1129a066db5f9448
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390183"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a>Habilitar o registro de detalhes de chamada Skype for Business Server

**Resumo:** Saiba como habilitar registros de registro de detalhes de chamada (CDR) no Skype for Business Server.

O CDR (registro de detalhes de chamada) registra informações de uso e diagnóstico sobre atividades ponto a ponto, incluindo mensagens de instância, chamadas VoIP (Voice over Internet Protocol), compartilhamento de aplicativos, transferência de arquivo e reuniões. Os dados de uso podem ser utilizados para calcular o retorno sobre o investimento, enquanto os dados de diagnóstico podem ser usados para solucionar problemas de atividades ponto a ponto e reuniões.

Use o procedimento a seguir para habilitar a CDR para toda a sua organização ou cada site em sua organização.

> [!NOTE]
> Para habilitar a CDR, você deve configurar o monitoramento e um banco de dados de monitoramento. Para obter detalhes, consulte [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a>Para habilitar a CDR com Skype for Business Server Painel de Controle

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou Skype for Business Server.

2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.

3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Registro de Detalhes de Chamada**.

4. Na página **Registro de Detalhes de** Chamada, clique no site apropriado da tabela, clique em **Ação** e em **Habilitar CDR**.

    > [!NOTE]
    > A CDR está habilitada por padrão.

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>Habilitando a CDR usando Windows PowerShell cmdlets

Você pode habilitar a CDR usando Windows PowerShell e o cmdlet **Set-CsCdrConfiguration**. Você pode executar esse cmdlet no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. Para obter detalhes sobre como usar Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte [Administração do Microsoft Lync Remote PowerShell](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). O processo é o mesmo no Skype for Business Server.

### <a name="to-enable-cdr-for-a-single-location"></a>Para habilitar a CDR para um único local

 Para desabilitar o CDR, de definir o parâmetro EnableCDR como True ($True).

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a>Para desabilitar o CDR para um único local

 Para desabilitar o CDR, de definir o parâmetro EnableCDR como False ($False). Desabilitar a CDR não desinstala o monitoramento. Ele pausa a coleção e o armazenamento de dados cdr.

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>Para usar um único comando para habilitar o CDR em vários locais

 Esse comando habilita a CDR para todas as configurações de CDR em uso na sua organização.

  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

Para obter mais informações, consulte o tópico de ajuda do cmdlet [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .

## <a name="see-also"></a>Confira também

[Planejamento do monitoramento](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[Implantando o monitoramento](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)