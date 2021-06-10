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
description: Saiba como instalar e configurar o Teams para Surface Hub para que Teams seja o aplicativo padrão de chamada e reuniões.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Devices
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 38202fcbb4c2147baae3f745bc2455da6fdff3e3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093931"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>Implantar o Microsoft Teams para o Surface Hub
======================================

Antes de instalar Teams para Surface Hub, certifique-se de fazer o seguinte:

 □ Certifique-se de que hardware, sistema operacional e outros requisitos sejam atendidos. Para obter mais informações, consulte o [guia Microsoft Surface Hub administrador](/surface-hub/).<br>
 □ certifique-se de que a atualização mínima do sistema operacional necessária para Teams está instalada - [KB4343889](https://support.microsoft.com/help/4343889).<br>
 □ atribuir uma Teams de usuário à conta do dispositivo Hub.<br>
 □ Se você estiver fazendo a transição do Skype for Business Online, confirme se uma licença Teams é atribuída ao usuário.

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Instalar Teams para Surface Hub do Microsoft Store 

Estas instruções são para instalar Teams para Surface Hub do Microsoft Store. 
 
1. Inicie o Microsoft Store:<br>
   a. Toque **em Iniciar** Todos os  >    >  **Aplicativos Configurações**.<br> b. Toque **Surface Hub conta de dispositivo, gerenciamento**.<br>
   c. À esquerda, toque na **guia Aplicativos & Recursos.**<br> d. À direita, toque no **botão Abrir Loja.** 
2. Na Microsoft Store, pesquise *Microsoft Teams*. O **Microsoft Teams para Surface Hub** será exibido. Toque no **botão Obter o aplicativo** para instalar.  
3. Quando a instalação for concluída, reinicie o Surface Hub. 

> [!NOTE]
> Não toque em **Iniciar** na página de listagem da Loja.

## <a name="make-teams-the-default-calling-and-meetings-application"></a>Tornar Teams aplicativo de reuniões e chamada padrão
 
Há duas opções para configurar a política de aplicativo de chamada e reuniões padrão: 

- **Opção 1**: Configurar por meio de chave USB. 
- **Opção 2**: Configurar via MDM, como o Intune.
 
### <a name="option-1-configure-via-usb-key"></a>Opção 1: Configurar por meio de chave USB 
 
Os pacotes podem ser encontrados nesta [página de download.](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g) Escolha o apropriado para o pacote que você está planejando instalar e copiá-lo para uma chave USB. O arquivo .ppkg correto a ser usado depende da política de aplicativo padrão que você gostaria de aplicar da seguinte maneira: 

|Número  |Descrição  |
|---------|---------|
|0     | Skype aplicativo preferencial na Tela Inicial, Teams Reuniões disponíveis        |
|1     | Teams aplicativo preferencial na Tela Inicial, Skype Reuniões disponíveis        |
|2     | Teams aplicativo exclusivo na tela Inicial (Skype aplicativo não disponível)        |
 
1. Anexe a chave USB ao Surface Hub dispositivo. 
2. Abra o **Configurações** em um Surface Hub dispositivo. 
3. Abra **Surface Hub Gerenciamento de Conta de Dispositivo.**
4. Open **Device Management**. 
5. Clique **em Adicionar ou Remover um pacote de provisionamento.** 
6. Clique **em Adicionar Pacote**.
7. Selecione a **opção Mídia Removível** no menu suspenso. 
8. Adicione o pacote <strong>teamsRTMMode*.ppkg</strong> apropriado que foi copiado anteriormente para a chave USB. 
9. Reinicie o Surface Hub dispositivo. 
10. Depois que o dispositivo é reiniciado, você deve ser capaz de iniciar o aplicativo Teams a partir da tela Inicial e participar de uma reunião do calendário. 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>Opção 2: Configurar via MDM, como o Intune 

Use o seguinte para configurar a política de aplicativo de chamada e reuniões padrão por meio do Intune. Consulte também o blog, [Deploy the Microsoft Teams for Surface Hub app using Intune](https://y0av.me/2018/07/16/deploy-the-microsoft-teams-for-surface-hub-app-using-intune/).

|Configuração   |Valor    |Descrição    |
|----------|---------|---------|
|Path      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|Tipo de dados | integer (0-2)   |0 - Skype aplicativo preferencial na Tela Inicial, Teams Reuniões disponíveis<br>1 - Teams aplicativo preferencial na Tela Inicial, Skype Reuniões disponíveis<br>2 - Teams aplicativo exclusivo na tela Inicial (Skype aplicativo não disponível) |
|Operações| Obter, Definir        |

|Configuração   |Valor    |
|----------|---------|
|Path      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|Tipo de dados | string - definir cadeia de caracteres como Teams ID do pacote de aplicativos **como Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams** |
|Operações| Obter, Definir        |

Reinicie o Surface Hub dispositivo. Depois que o dispositivo é reiniciado, você deve ser capaz de iniciar o aplicativo Teams a partir da tela Inicial e participar de uma reunião do calendário.