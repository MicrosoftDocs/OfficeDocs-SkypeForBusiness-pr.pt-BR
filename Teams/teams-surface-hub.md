---
title: Implantar o Microsoft Teams para o Surface Hub
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/04/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Definir configurações de administrador para o Microsoft Teams para Surface Hub.
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 37c38577fe3bda9ed2a1c2e224390e89f44de96b
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570097"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>Implantar o Microsoft Teams para o Surface Hub
======================================

Antes de instalar o Microsoft Teams para Surface Hub, certifique-se de fazer o seguinte:

 □ Certifique-se de que o hardware, sistema operacional e outros requisitos sejam atendidos. Para obter mais informações, consulte o [Guia de administração do Microsoft Surface Hub](https://docs.microsoft.com/surface-hub/).<br>
 □ Certifique-se de que a atualização mínima do sistema operacional necessária para o Microsoft Teams esteja instalada- [KB4343889](https://support.microsoft.com/help/4343889).<br>
 □ Atribuir uma licença do teams à conta de dispositivo Hub.<br>
 □ Se você estiver migrando do Skype for Business Online, confirme se há uma licença do teams atribuída ao usuário.

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Instalar o Microsoft Teams para Surface Hub na Microsoft Store 

Estas instruções são para a instalação do teams para Surface Hub na Microsoft Store. 
 
1. Inicie a Microsoft Store:<br>
   a. Toque em **Iniciar** > **todas** > **as configurações**de aplicativos.<br> b. Toque em **conta de dispositivo Hub Surface, gerenciamento**.<br>
   c. À esquerda, toque na guia **aplicativos & recursos** .<br> d. À direita, toque no botão **abrir loja** . 
2. Na Microsoft Store, procure *Microsoft Teams*. O **Microsoft Teams para Surface Hub** será exibido. Toque no botão **obter aplicativo** para instalar.  
3. Quando a instalação estiver concluída, reinicie o Surface Hub. 

> [!NOTE]
> Não toque em **Iniciar** na página listagem da loja.

## <a name="make-teams-the-default-calling-and-meetings-application"></a>Torne as equipes o aplicativo de chamadas e reuniões padrão
 
Há duas opções para configurar a política de aplicativo de chamada e de reunião padrão: 

- **Opção 1**: configurar via chave USB. 
- **Opção 2**: configurar via MDM, como o Intune.
 
### <a name="option-1-configure-via-usb-key"></a>Opção 1: configurar via chave USB 
 
Os pacotes podem ser encontrados nesta [página de download](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g). Selecione o nome apropriado para o pacote que você pretende instalar e copie-o para uma chave USB. O arquivo. ppkg correto a ser usado depende da política de aplicativo padrão que você gostaria de aplicar da seguinte maneira: 

|Número  |Descrição  |
|---------|---------|
|0     | Aplicativo preferencial do Skype na tela inicial, reuniões do teams disponíveis        |
|1     | Aplicativo preferido do teams na tela inicial, reuniões do Skype disponíveis        |
|2     | Aplicativo exclusivo do teams na tela inicial (aplicativo Skype não disponível)        |
 
1. Anexe a chave USB ao dispositivo do Surface Hub. 
2. Abra o aplicativo **configurações** em um dispositivo Surface Hub. 
3. **Gerenciamento de conta de dispositivo do Surface Hub**aberto.
4. Abra o **Gerenciamento de dispositivo**. 
5. Clique em **Adicionar ou remover um pacote de provisionamento**. 
6. Clique em **Adicionar pacote**.
7. Selecione a opção **mídia removível** no menu suspenso. 
8. Adicione o pacote <strong>TeamsRTMMode *. ppkg</strong> apropriado que foi copiado anteriormente para a chave USB. 
9. Reinicie o dispositivo do Surface Hub. 
10. Depois que o dispositivo for reiniciado, você poderá iniciar o aplicativo Teams a partir da tela inicial e ingressar em uma reunião a partir do calendário. 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>Opção 2: configurar via MDM, como o Intune 

Use o seguinte para configurar a política de aplicativos de reuniões e chamadas padrão via Intune. Consulte também o blog, [implante o aplicativo Microsoft Teams para Surface Hub usando o Intune](https://y0av.me/2018/07/16/deploy-the-microsoft-teams-for-surface-hub-app-using-intune/).

|Configuração   |Valor    |Descrição    |
|----------|---------|---------|
|Path      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|Tipo de dados | inteiro (0-2)   |0-aplicativo preferido pelo Skype na tela inicial, reuniões do teams disponíveis<br>1-aplicativo preferencial para equipes na tela inicial, reuniões do Skype disponíveis<br>2-aplicativo exclusivo para equipes na tela inicial (aplicativo Skype não disponível) |
|Operações| Obter, definir        |

|Configuração   |Valor    |
|----------|---------|
|Path      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|Tipo de dados | String-define a cadeia de caracteres para a ID do pacote do aplicativo Teams como **Microsoft. MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe! Teams** |
|Operações| Obter, definir        |

Reinicie o dispositivo do Surface Hub. Depois que o dispositivo for reiniciado, você poderá iniciar o aplicativo Teams a partir da tela inicial e ingressar em uma reunião a partir do calendário.

