---
title: Usar o PowerShell para tarefas no menu Cliente
ms.reviewer: ''
ms.author: v-smandalika
author: v-smandalika
manager: dansimp
ms.date: 10/12/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 'Resumo: Skype for Business Server painel de controle para mapeamento de Cmdlet.'
ms.openlocfilehash: e4d72aad28167e3be427f203b8e5b80e2305a636
ms.sourcegitcommit: b57e19e20900ff02f3196c811bf1dd1acd149c79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/26/2021
ms.locfileid: "60579712"
---
# <a name="client"></a>Client

Este artigo descreve como resultados semelhantes aos do **item** de menu Cliente no Painel de Controle herdado podem ser obtidos usando cmdlets.

Este artigo descreve os seguintes sub-menus:

- [Cliente](#client)
  - [Política de versão do cliente](#client-version-policy)
  - [Configuração de Versão de Cliente](#client-version-configuration)
  - [Atualização de Dispositivos](#device-update)
  - [Dispositivo de Teste](#test-device)
  - [Configuração do Log de Dispositivos](#device-log-configuration)
  - [Configuração do dispositivo](#device-configuration)
  - [Política de Mobilidade](#mobility-policy)
  - [Configuração de Notificação por Push](#push-notification-configuration)

## <a name="client-version-policy"></a>Política da Versão de Cliente

O item de sub menu **POLÍTICA DE VERSÃO** DO CLIENTE no menu Cliente retorna informações sobre os clientes com suporte no Skype for Business Server ambiente.  Uma política de versão do cliente permite que você especifique os clientes que podem entrar no Skype for Business Server sistema.

Considere as várias tarefas que um usuário pode realizar na POLÍTICA DE VERSÃO DO CLIENTE **e** os cmdlets Skype for Business essas tarefas são mapeados.

---
> **Cenário 1**: listar todas as políticas de versão do cliente

   ![Listar Política de Versão do Cliente](./media/clientversionpolicy-1.png)

***Cmdlet***

[Get-CsClientVersionPolicy](/powershell/module/skype/get-csclientversionpolicy)

***Exemplo***

```powershell
 Get-CsClientVersionPolicy
```

---

> **Cenário 2**: Criar uma nova política de versão do cliente

   ![Nova política de versão do cliente](./media/clientversionpolicy-2.png)

***Cmdlet***

[New-CsClientVersionPolicy](/powershell/module/skype/new-csclientversionpolicy)  

***Exemplo***

```powershell
 New-CsClientVersionPolicy -Identity site:Redmond
```

---

> **Cenário 3**: Obter detalhes de uma política de versão do cliente escolhida

   ![Obter Política de Versão do Cliente](./media/clientversionpolicy-3.png)

***Cmdlet***

[Get-CsClientVersionPolicy](/powershell/module/skype/get-csclientversionpolicy)

***Exemplo***

```powershell
 Get-CsClientVersionPolicy -Identity site:Redmond
```

---

> **Cenário 4**: Excluir políticas de versão do cliente escolhidas

   ![Excluir Política de Versão do Cliente](./media/clientversionpolicy-4.png)

***Cmdlet***

[Remove-CsClientVersionPolicy](/powershell/module/skype/remove-csclientversionpolicy)

***Exemplo***

```powershell
 Remove-CsClientVersionPolicy -Identity site:Redmond
```

---

> **Cenário 5**: Atualizar uma política de versão do cliente

   ![Atualizar Política de Versão do Cliente](./media/clientversionpolicy-5.png)

- **Anotação 1 - Resultado**

    Essa anotação na imagem indica um resultado, ou seja, os dados que estão sendo recuperados e exibidos.

    ***Cmdlet***

    [Get-CsClientVersionPolicyRule](/powershell/module/skype/get-csclientversionpolicyrule)

    ***Exemplo***

    ```powershell
    Get-CsClientVersionPolicyRule -Filter "Global/*"
    ```

- **Anotação 2 - Opção (para o usuário)**

    Essa anotação na imagem indica uma opção para o usuário implementar, ou seja, obter os detalhes das regras de política de versão do cliente.

    ***Cmdlet***

    [Get-CsClientVersionPolicyRule](/powershell/module/skype/get-csclientversionpolicyrule)

    ***Exemplo***

    ```powershell
    Get-CsClientVersionPolicyRule -Identity "Global/2336c611-a243-4c5d-994b-eea8a524d0e4"
    ```

- **Anotação 3 - Opção (para o usuário)**

    Essa anotação na imagem indica uma opção para o usuário implementar, ou seja, criar uma nova regra de política de versão do cliente.

    ***Cmdlet***

    [New-CsClientVersionPolicyRule](/powershell/module/skype/new-csclientversionpolicyrule)

    ***Exemplo***

    ```powershell
    $x = \[guid\]::NewGuid()

    New-CsClientVersionPolicyRule -Parent "site:Redmond" -RuleId $x -MajorVersion 4 -UserAgent InHouse
    ```

- **Anotação 4 - Opção (para o usuário)**

    Essa anotação na imagem indica uma opção para o usuário implementar, ou seja, a regra de política de versão do cliente recém-criada.

    ***Cmdlet***

    [Set-CsClientVersionPolicy](/powershell/module/skype/set-csclientversionpolicy)

    ***Exemplo***

    ```powershell
    Set-CsClientVersionPolicy -Identity site:Redmond -Rules $Null

    $x = Get-CsClientVersionPolicy -Identity site:Dublin | Select-Object -ExpandProperty Rules

    Set-CsClientVersionPolicy -Identity site:Redmond -Rules $x
    ```

---

## <a name="client-version-configuration"></a>Configuração da Versão de Cliente

 O **sub-menu CONFIGURAÇÃO DA** VERSÃO DO CLIENTE retorna informações sobre os clientes com suporte no Skype for Business Server ambiente.

Considere as várias tarefas que um usuário pode realizar na CONFIGURAÇÃO DA VERSÃO DO CLIENTE **e** os cmdlets Skype for Business essas tarefas são mapeados.

---
> **Cenário 1**: Listar todas as configurações de versão do cliente

   ![Listar configuração de versão do cliente](./media/ClientVersionConfiguration-1.png)

***Cmdlet***

[Get-CsClientVersionConfiguration](/powershell/module/skype/get-csclientversionconfiguration)

***Exemplo***

```powershell
 Get-CsClientVersionConfiguration
```

---

> **Cenário 2**: Criar uma nova configuração de versão do cliente

   ![Criar Configuração de Versão do Cliente](./media/ClientVersionConfiguration-2.png)

***Cmdlet***

[New-CsClientVersionConfiguration](/powershell/module/skype/new-csclientversionconfiguration)  

***Exemplo***

```powershell
 New-CsClientVersionConfiguration -Identity site:Redmond -Enabled $False
```

---

> **Cenário 3**: Obter detalhes de uma configuração de versão do cliente escolhida

   ![Obter Configuração da Versão do Cliente](./media/ClientVersionConfiguration-3.png)

***Cmdlet***

[Get-CsClientVersionConfiguration](/powershell/module/skype/get-csclientversionconfiguration)

***Exemplo***

```powershell
 Get-CsClientVersionConfiguration -Identity site:Redmond
```

---

> **Cenário 4**: Excluir configurações de versão do cliente escolhidas

   ![Excluir Configuração de Versão do Cliente](./media/ClientVersionConfiguration-4.png)

***Cmdlet***

[Remove-CsClientVersionConfiguration](/powershell/module/skype/remove-csclientversionconfiguration)

***Exemplo***

```powershell
 Remove-CsClientVersionConfiguration -Identity site:Redmond
```

---

> **Cenário 5**: Atualizar uma configuração de versão do cliente

   ![Atualizar a configuração da versão do cliente](./media/ClientVersionConfiguration-5.png)

***Cmdlet***

[Set-CsClientVersionConfiguration](/powershell/module/skype/set-csclientversionconfiguration)

***Exemplo***

```powershell
Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration -DefaultURL "https://litwareinc.com/csclients"
```

---

> **Cenário 6**: Habilitar/desabilitar configurações de versão do cliente

![Habilitar a configuração de versão do cliente](./media/ClientVersionConfiguration-6.png)

***Cmdlet***

[Set-CsClientVersionConfiguration](/powershell/module/skype/set-csclientversionconfiguration)

***Exemplo***

```powershell
Set-CsClientVersionConfiguration -Identity site:Redmond -Enabled $False
```

---

## <a name="device-update"></a>Atualização de Dispositivo

**As regras DE ATUALIZAÇÃO** DE DISPOSITIVO são usadas para associar atualizações de firmware a dispositivos que Skype for Business Telefone Edition.

Vamos considerar as várias tarefas que um usuário pode realizar no **DEVICE UPDATE** e os cmdlets Skype for Business essas tarefas são mapeados.

---
> **Cenário 1**: Listar todas as atualizações de dispositivo

   ![Listar Atualização de Dispositivo](./media/device-update-1.png)

***Cmdlet***

[Get-CsDeviceUpdateRule](/powershell/module/skype/get-csdeviceupdaterule)

***Exemplo***

```powershell
 Get-CsDeviceUpdateRule
```

---

> **Cenário 2**: Excluir atualizações de dispositivo

   ![Excluir Atualização de Dispositivo](./media/device-update-2.png)

***Cmdlet***

[Remove-CsDeviceUpdateRule](/powershell/module/skype/remove-csdeviceupdaterule)  

***Exemplo***

```powershell
 Remove-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9
```

---

> **Cenário 3**: Cancelar atualizações de dispositivo

   ![Cancelar Atualização de Dispositivo](./media/device-update-3.png)

***Cmdlet***

[Clear-CsDeviceUpdateFile](/powershell/module/skype/clear-csdeviceupdatefile)

***Exemplo***

```powershell
 Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"
```

---

> **Cenário 4**: Aprovar atualizações de dispositivos

   ![Aprovar Atualização de Dispositivo](./media/device-update-4.png)

***Cmdlet***

[Approve-CsDeviceUpdateRule](/powershell/module/skype/approve-csdeviceupdaterule)

***Exemplo***

```powershell
 Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9
```

---

> **Cenário 5**: Restaurar atualizações de dispositivo

   ![Restaurar Atualização de Dispositivo](./media/device-update-5.png)

***Cmdlet***

[Restore-CsDeviceUpdateRule](/powershell/module/skype/restore-csdeviceupdaterule)

***Exemplo***

```powershell
 Restore-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9
```

---

## <a name="test-device"></a>Dispositivo de Teste

O item de sub-menu TEST **DEVICE** fornece uma maneira para os administradores testarem atualizações de firmware antes que essas atualizações sejam distribuídas para todos os dispositivos de uma organização.

Considere as várias tarefas que um usuário pode realizar no **TEST DEVICE** e os cmdlets Skype for Business essas tarefas são mapeados.

---
> **Cenário 1**: Listar todos os dispositivos de teste

   ![Dispositivo de Teste de Lista](./media/testdevice-1.png)

***Cmdlet***

[Get-CsTestDevice](/powershell/module/skype/get-cstestdevice)

***Exemplo***

```powershell
 Get-CsTestDevice
```

---

> **Cenário 2**: Criar um novo dispositivo de teste

   ![Criar Dispositivo de Teste](./media/testdevice-2.png)

***Cmdlet***

[New-CsTestDevice](/powershell/module/skype/new-cstestdevice)  

***Exemplo***

```powershell
 New-CsTestDevice -Identity site:Redmond/UCPhone -IdentifierType SerialNumber -Identifier "07823-A345"
```

---

> **Cenário 3**: Obter detalhes de um dispositivo de teste escolhido

   ![Obter Dispositivo de Teste](./media/testdevice-3.png)

***Cmdlet***

[Get-CsTestDevice](/powershell/module/skype/get-cstestdevice)

***Exemplo***

```powershell
 Get-CsTestDevice -Identity site:Redmond/UCPhone
```

---

> **Cenário 4**: Excluir dispositivos de teste escolhidos

   ![Excluir Dispositivo de Teste](./media/testdevice-4.png)

***Cmdlet***

[Remove-CsTestDevice](/powershell/module/skype/remove-cstestdevice)

***Exemplo***

```powershell
 Remove-CsTestDevice -Identity site:Redmond
```

---

> **Cenário 5**: Atualizar um dispositivo de teste

   ![Atualizar Dispositivo de Teste](./media/testdevice-5.png)

***Cmdlet***

[Set-CsTestDevice](/powershell/module/skype/set-cstestdevice)

***Exemplo***

```powershell
Set-CsTestDevice -Identity site:Redmond/UCPhone -IdentifierType SerialNumber -Identifier "09768-ABDR-83295"
```

---

## <a name="device-log-configuration"></a>Configuração do Log de Dispositivos

O item **do** sub menu CONFIGURAÇÃO DE LOG DE DISPOSITIVO ajuda a gerenciar o serviço Web de Atualização de Dispositivo, um componente Skype for Business Server que permite que os administradores distribuam atualizações de firmware para telefones e outros dispositivos que são executados Skype for Business.

Vamos considerar as várias tarefas que um usuário pode realizar na CONFIGURAção de **LOG** do DISPOSITIVO e os cmdlets Skype for Business essas tarefas são mapeados.

---
> **Cenário 1**: listar todas as configurações de log de dispositivos

   ![Listar Configuração de Log de Dispositivo](./media/device-log-configuration-1.png)

***Cmdlet***

[Get-CsDeviceUpdateConfiguration](/powershell/module/skype/get-csdeviceupdateconfiguration)

***Exemplo***

```powershell
 Get-CsDeviceUpdateConfiguration
```

---

> **Cenário 2**: Criar uma nova configuração de log de dispositivo

   ![Criar Configuração de Log de Dispositivo](./media/device-log-configuration-2.png)

***Cmdlet***

[New-CsDeviceUpdateConfiguration](/powershell/module/skype/new-csdeviceupdateconfiguration)  

***Exemplo***

```powershell
 New-CsDeviceUpdateConfiguration -Identity site:Redmond "07823-A345"
```

---

> **Cenário 3**: Obter detalhes de uma configuração de log de dispositivo escolhida

   ![Obter Configuração de Log de Dispositivo](./media/device-log-configuration-3.png)

***Cmdlet***

[Get-CsDeviceUpdateConfiguration](/powershell/module/skype/get-csdeviceupdateconfiguration)

***Exemplo***

```powershell
 Get-CsDeviceUpdateConfiguration -Identity Global
```

---

> **Cenário 4**: Excluir configurações de log de dispositivo escolhidas

   ![Excluir Configuração de Log de Dispositivo](./media/device-log-configuration-4.png)

***Cmdlet***

[Remove-CsDeviceUpdateConfiguration](/powershell/module/skype/remove-csdeviceupdateconfiguration)

***Exemplo***

```powershell
 Remove-CsDeviceUpdateConfiguration -Identity site:Redmond
```

---

> **Cenário 5**: Atualizar uma configuração de log de dispositivo

   ![Atualizar Configuração de Log de Dispositivo](./media/device-log-configuration-5.png)

***Cmdlet***

[Set-CsDeviceUpdateConfiguration](/powershell/module/skype/set-csdeviceupdateconfiguration)

***Exemplo***

```powershell
Set-CsDeviceUpdateConfiguration -Identity global -MaxLogFileSize 2048000 -MaxLogCacheLimit 1024000
```

---

## <a name="device-configuration"></a>Configuração do dispositivo

O item do sub menu **CONFIGURAÇÃO** DO DISPOSITIVO ajuda a administrar informações sobre opções de gerenciamento para telefones UC. Essas opções incluem o modo de segurança necessário e se o telefone deve ou não ser bloqueado automaticamente após um período especificado de inatividade.

Vamos considerar as várias tarefas que um usuário pode realizar na CONFIGURAÇÃO DO DISPOSITIVO **e** os cmdlets Skype for Business essas tarefas são mapeados.

---

> **Cenário 1**: listar todas as políticas de mobilidade

   ![Listar Configuração do Dispositivo](./media/device-configuration-1.png)

***Cmdlet***

[Get-CsUCPhoneConfiguration](/powershell/module/skype/get-csucphoneconfiguration)

***Exemplo***

```powershell
 Get-CsUCPhoneConfiguration
```

---

> **Cenário 2**: Criar uma nova configuração de dispositivo

   ![Criar Configuração de Dispositivo](./media/device-configuration-2.png)

***Cmdlet***

[New-CsUCPhoneConfiguration](/powershell/module/skype/new-csucphoneconfiguration)  

***Exemplo***

```powershell
 New-CsUCPhoneConfiguration -Identity site:Redmond -CalendarPollInterval "00:10:00" -LoggingLevel "Medium"
```

---

> **Cenário 3**: Obter detalhes de uma configuração de dispositivo escolhida

   ![Obter Configuração do Dispositivo](./media/device-configuration-3.png)

***Cmdlet***

[Get-CsUCPhoneConfiguration](/powershell/module/skype/get-csucphoneconfiguration)

***Exemplo***

```powershell
 Get-CsUCPhoneConfiguration -Identity site:Redmond
```

---

> **Cenário 4**: Excluir configurações de dispositivo escolhidas

   ![Excluir Configuração do Dispositivo](./media/device-configuration-4.png)

***Cmdlet***

[Remove-CsUCPhoneConfiguration](/powershell/module/skype/remove-csucphoneconfiguration)

***Exemplo***

```powershell
 Remove-CsUCPhoneConfiguration -Identity site:Redmond
```

---

> **Cenário 5**: atualiza uma configuração de dispositivo

   ![Atualizar Configuração do Dispositivo](./media/device-configuration-5.png)

***Cmdlet***

[Set-CsUCPhoneConfiguration](/powershell/module/skype/set-csucphoneconfiguration)

***Exemplo***

```powershell
 Set-CsUCPhoneConfiguration -Identity site:Redmond -PhoneLockTimeout "00:30:00"
```

---

## <a name="mobility-policy"></a>Política de Mobilidade

**A POLÍTICA de MOBILIDADE** determina se um usuário pode ou não usar o Skype for Business Mobile. Essas políticas também gerenciam a capacidade de um usuário para empregar a Chamada via Trabalho, um recurso que permite aos usuários fazer e receber chamadas telefônicas em seus celulares usando seu número de telefone comercial em vez do seu número de celular. As políticas de mobilidade também podem ser usadas para tornar Wi-Fi conexões um requisito ao fazer ou receber chamadas.

Considere as várias tarefas que um usuário pode realizar na **POLÍTICA DE** MOBILIDADE e os cmdlets Skype for Business essas tarefas são mapeados.

---

> **Cenário 1**: listar todas as políticas de mobilidade

   ![Política de Mobilidade de Lista](media/mobility-policy-1.png)

***Cmdlet***

[Get-CsMobilityPolicy](/powershell/module/skype/get-csmobilitypolicy)

***Exemplo***

```powershell
 Get-CsMobilityPolicy
```

---

> **Cenário 2**: Criar uma nova política de mobilidade

   ![Criar Política de Mobilidade](./media/mobility-policy-2.png)

***Cmdlet***

[New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy)  

***Exemplo***

```powershell
 New-CsMobilityPolicy -Identity site:Redmond -EnableOutsideVoice $False
```

---

> **Cenário 3**: Obter detalhes de uma política de mobilidade escolhida

   ![Obter Política de Mobilidade](./media/mobility-policy-3.png)

***Cmdlet***

[Get-CsMobilityPolicy](/powershell/module/skype/get-csmobilitypolicy)

***Exemplo***

```powershell
 Get-CsMobilityPolicy -Identity "site:Redmond"
```

---

> **Cenário 4**: Excluir políticas de mobilidade escolhidas

   ![Excluir Política de Mobilidade](./media/mobility-policy-4.png)

***Cmdlet***

[Remove-CsMobilityPolicy](/powershell/module/skype/remove-csmobilitypolicy)

***Exemplo***

```powershell
 Remove-CsMobilityPolicy -Identity "site:Redmond"
```

---

> **Cenário 5**: atualizar uma política de mobilidade

   ![Atualizar Política de Mobilidade](./media/mobility-policy-5.png)

***Cmdlet***

[Set-CsMobilityPolicy](/powershell/module/skype/set-csmobilitypolicy)

***Exemplo***

```powershell
Set-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False
```

---

## <a name="push-notification-configuration"></a>Configuração de Notificação por Push

O serviço de notificação por push (Serviço de Notificação por Push da Apple e Serviço de Notificação por Push da Microsoft) oferece uma maneira de enviar notificações sobre eventos como novas mensagens instantâneas ou novas mensagens de voz para dispositivos móveis, como iPhones e telefones Windows. Essas notificações são configuradas para serem enviadas mesmo que o aplicativo Skype for Business nesses dispositivos seja suspenso ou executado em segundo plano.

Considere as várias tarefas que um usuário pode realizar na CONFIGURAÇÃO DE NOTIFICAÇÃO POR **PUSH** e os cmdlets Skype for Business essas tarefas são mapeados.

---

> **Cenário 1**: listar todas as políticas de mobilidade

   ![Listar Configuração de Notificação por Push](./media/push-notification-config-1.png)

***Cmdlet***

[Get-CsPushNotificationConfiguration](/powershell/module/skype/get-cspushnotificationconfiguration)

***Exemplo***

```powershell
 Get-CsPushNotificationConfiguration
```

---

> **Cenário 2**: Criar uma nova configuração de notificação por push

   ![Criar Configuração de Notificação por Push](./media/push-notification-config-2.png)

***Cmdlet***

[New-CsPushNotificationConfiguration](/powershell/module/skype/new-cspushnotificationconfiguration)  

***Exemplo***

```powershell
 New-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService -$True
```

---

> **Cenário 3**: Obter detalhes de uma configuração de notificação por push escolhida

   ![Obter Configuração de Notificação por Push](./media/push-notification-config-3.png)

***Cmdlet***

[Get-CsPushNotificationConfiguration](/powershell/module/skype/get-cspushnotificationconfiguration)

***Exemplo***

```powershell
 Get-CsPushNotificationConfiguration -Identity "site:Redmond"
```

---

> **Cenário 4**: Excluir configurações de notificação por push escolhidas

   ![Excluir Configuração de Notificação por Push](./media/push-notification-config-4.png)

***Cmdlet***

[Remove-CsPushNotificationConfiguration](/powershell/module/skype/remove-cspushnotificationconfiguration)

***Exemplo***

```powershell
 Remove-CsPushNotificationConfiguration -Identity "site:Redmond"
```

---

> **Cenário 5**: Atualizar uma configuração de notificação por push

   ![Atualizar Configuração de Notificação por Push](./media/push-notification-config-5.png)

***Cmdlet***

[Set-CsPushNotificationConfiguration](/powershell/module/skype/set-cspushnotificationconfiguration)

***Exemplo***

```powershell
 Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False
```

---
