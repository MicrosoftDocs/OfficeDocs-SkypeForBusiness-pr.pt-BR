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
description: Defina configurações de administração for Microsoft Teams para o Hub de superfície.
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: add4b7ece81fd2c4184453b03c889a27982c830b
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460112"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>Implantar o Microsoft Teams para o Surface Hub
======================================

Antes de instalar as equipes do Hub de superfície, certifique-se de fazer o seguinte:

 Hardware do □ tornar-se de que, sistema operacional e outros requisitos são atendidos. Para obter mais informações, consulte o [guia de administração do Microsoft Surface Hub](https://docs.microsoft.com/surface-hub/).<br>
 □ Verifique se a atualização mínima do sistema operacional necessária para equipes está instalada - [KB4343889](https://support.microsoft.com/help/4343889).<br>
 □ Atribuir uma licença de equipes para a conta de dispositivo de Hub.<br>
 □ Se você estiver transição do Skype para negócios Online, confirme que uma licença de equipes é atribuída ao usuário.

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Instalar equipes para o Hub de superfície do repositório de Microsoft 

Essas instruções são para a instalação de equipes para o Hub de superfície do Microsoft Store. 
 
1. Inicie o repositório da Microsoft:<br>
   a. Toque em **Iniciar** > **todos os aplicativos** > **configurações**.<br> b. Toque em **conta de dispositivo do Hub de superfície, gerenciamento**.<br>
   c. À esquerda, toque na guia **aplicativos & recursos** .<br> d. À direita, toque no botão **Abrir armazenamento** . 
2. Do Microsoft Store, procure *As equipes da Microsoft*. As **Equipes da Microsoft para o Hub de superfície** será exibida. Toque no botão **obter o aplicativo** para instalar.  
3. Quando a instalação estiver concluída, reinicie o Hub de superfície. 

> [!NOTE]
> Não toque na **inicialização** do repositório de página de listagem.

## <a name="make-teams-the-default-calling-and-meetings-application"></a>Tornar as equipes a chamada padrão e a aplicação de reuniões
 
Há duas opções para configurar a política padrão de aplicativo de chamada e reuniões: 

- **Opção 1**: configurar via chave USB. 
- **Opção 2**: configurar via MDM como Intune.
 
### <a name="option-1-configure-via-usb-key"></a>Opção 1: Configurar via chave USB 
 
Os pacotes podem ser encontrados na [página de download](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g). Selecione a adequada para o pacote que você estiver planejando instalar e copiá-lo para uma chave USB. O arquivo .ppkg correto a ser usado depende a diretiva de aplicação de padrão que você gostaria de aplicar da seguinte maneira: 

|Número  |Descrição  |
|---------|---------|
|0     | App preferencial do Skype na tela Iniciar, equipes de reuniões disponíveis        |
|1     | As equipes de app preferencial na tela Iniciar, Skype reuniões disponíveis        |
|2     | Equipes de aplicativo exclusivo na tela Iniciar (Skype app não disponível)        |
 
1. Anexe a chave USB com o dispositivo do Hub de superfície. 
2. Abra o aplicativo de **configurações** em um dispositivo do Hub de superfície. 
3. Abra o **gerenciamento de contas de dispositivo do Hub de superfície**.
4. Abra o **gerenciamento de dispositivo**. 
5. Clique em **Adicionar ou remover um pacote de provisionamento**. 
6. Clique em **Adicionar pacote**.
7. Selecione a opção de **Mídia removível** no menu suspenso. 
8. Adicione o pacote adequado <strong>TeamsRTMMode*.ppkg</strong> que anteriormente foi copiado para a chave USB. 
9. Reinicie o dispositivo do Hub de superfície. 
10. Depois que o dispositivo for reiniciado, você poderá iniciar o aplicativo de equipes na tela de início e ingressar em uma reunião do calendário. 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>Opção 2: Configurar via MDM como Intune 

Use o seguinte para configurar a chamada e reuniões aplicativo política padrão via Intune. Consulte também o blog, [implantar as equipes da Microsoft para aplicativo de superfície Hub usando Intune](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/).

|Configuração   |Valor    |Descrição    |
|----------|---------|---------|
|Path      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|Tipo de dados | inteiro (0-2)   |0 - app preferencial do Skype na tela Iniciar, equipes de reuniões disponíveis<br>1 - equipes preferencial app na tela Iniciar, Skype reuniões disponíveis<br>2 - equipes de aplicativo exclusivo na tela Iniciar (Skype app não disponível) |
|Operações| Obter, definir        |

|Configuração   |Valor    |
|----------|---------|
|Path      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|Tipo de dados | cadeia de caracteres - conjunto de cadeia de caracteres para a ID do pacote de aplicativo de equipes como **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe! As equipes** |
|Operações| Obter, definir        |

Reinicie o dispositivo do Hub de superfície. Depois que o dispositivo for reiniciado, você poderá iniciar o aplicativo de equipes na tela de início e ingressar em uma reunião do calendário.

