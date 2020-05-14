---
title: Implantar clientes para o Skype for Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Resumo: visão geral dos métodos de instalação de cliente Enterprise para o Skype for Business.'
ms.openlocfilehash: 8d6e59582c3c420d5752a84f793e6c3025b3c500
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220641"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Implantar clientes para o Skype for Business Server
 
**Resumo:** Visão geral dos métodos de instalação de cliente Enterprise para o Skype for Business.
  
O modo como você implanta o Skype for Business para seus usuários depende de você comprou o Skype for Business como parte de um plano do Microsoft 365 ou do Office 365 ou se comprou uma versão licenciada por volume do Skype for Business. 
  
- **Microsoft 365 ou Office 365** Se você tiver um plano do Microsoft 365 ou do Office 365 que inclua o Skype for Business, a tecnologia de instalação usada é chamada de clique para executar. Você pode permitir que seus usuários instalem o Skype for Business para eles a partir do centro de administração do Microsoft 365. Ou você pode implantar o Skype for Business em seus usuários baixando o software para sua rede local e usando suas ferramentas de implantação de software existentes, como o Microsoft Endpoint Configuration Manager. Para obter informações sobre a instalação do Skype for Business que acompanha o Microsoft 365 e o Office 365, consulte [implantar o cliente Skype for Business no microsoft 365 ou office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).
    
- **Volume licenciado** Se você tiver uma versão licenciada por volume do cliente do Skype for Business 2015 ou 2016, a tecnologia de instalação usada pelo Windows Installer (MSI). Um pacote de instalação baseado no Windows Installer consiste em vários arquivos MSI. Um pacote de núcleo MSI de linguagem neutra é combinado com um ou mais pacotes de linguagem específica para fazer um produto completo. A instalação reúne os pacotes individuais e efetua a personalização e tarefas de manutenção durante e após a instalação do Office nos computadores dos usuários. O cliente 2019 do Skype for Business usa instaladores de clique para executar.
    
Os tópicos desta seção descrevem como usar e personalizar o Windows Installer para implantar o cliente Skype for Business em seus usuários através de seus procedimentos normais.
  
> [!NOTE]
> O suplemento de reunião do Skype para o Microsoft Office, que oferece suporte ao gerenciamento de reuniões a partir do cliente de mensagens e colaboração do Outlook, é instalado automaticamente com clientes do Skype for Business. 
  
> [!NOTE]
> Os programas de instalação do Microsoft 365 e do Office 365 não desinstalam versões anteriores do Lync. O cliente Skype for Business instala lado a lado com outros clientes do Lync. 
  
## <a name="installing-windows-clients"></a>Instalando clientes do Windows

- [Personalizar a instalação do cliente Windows no Skype for Business Server](customize-windows-client-installation.md)
    
- [Configurar a experiência do cliente com o Skype for Business](configure-the-client-experience.md)
    
- [Configurar a lista de contatos inteligente no Skype for Business Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Instalando clientes de dispositivos

- [Instalar e testar o Skype for Business para Windows Phone](windows-phone.md)
    
- [Instalar e testar o Skype for Business para iOS](ios.md)
    
    
- [Implantar o plug-in de VDI do Lync com o Skype for Business Server](deploy-the-lync-vdi-plug-in.md)
    
- [Implantar clientes para download da Web no Skype for Business Server](deploy-web-downloadable-clients.md)
    
- [Personalizar a experiência do cliente Mac no Skype for Business](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Confira também

[Implantar o cliente Skype for Business no Microsoft 365 ou no Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
