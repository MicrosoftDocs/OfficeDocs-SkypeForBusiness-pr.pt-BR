---
title: Implantar clientes para o Skype para Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Resumo: Visão geral dos métodos de instalação de cliente enterprise para Skype para negócios.'
ms.openlocfilehash: db5b1a4ed51aed5986cd954af9cdbecab208647d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893459"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Implantar clientes para o Skype para Business Server
 
**Resumo:** Visão geral dos métodos de instalação de cliente enterprise para Skype para negócios.
  
Como você implanta Skype for Business para seus usuários depende se você comprou Skype para negócios como parte de um plano do Office 365 ou você comprou uma versão licenciada do volume do Skype para negócios. 
  
- **Office 365** Se você tiver um plano do Office 365 que inclui Skype para a empresa, a tecnologia de instalação que é usada é chamada Click-to-Run. Com o Office 365, você pode permitir que os usuários instalar Skype for Business para si próprios do portal do Office 365. Ou então, você pode implantar Skype for Business para seus usuários baixando o software em sua rede local e, em seguida, usando suas ferramentas de implantação de software existentes, tais como com o Microsoft System Center Configuration Manager. Para obter informações de instalação sobre Skype for Business que vem com o Office 365, consulte [Deploy a Skype para o cliente de negócios no Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).
    
- **Licença de volume** Se você tiver uma versão licenciada do volume do Skype para negócios 2015 ou cliente 2016, a tecnologia de instalação que é usada é o Windows Installer (MSI). Um pacote de instalação baseada no Windows Installer consiste em vários arquivos MSI. Um pacote de núcleo MSI de linguagem neutra é combinado com um ou mais pacotes de linguagem específica para fazer um produto completo. A instalação reúne os pacotes individuais e efetua a personalização e tarefas de manutenção durante e após a instalação do Office nos computadores dos usuários. O Skype para negócios 2019 cliente usa instaladores Click-to-Run.
    
Os tópicos desta seção descrevem como usar e personalizar o Windows Installer para implantar o Skype para o cliente de negócios para seus usuários por meio de seus procedimentos normais.
  
> [!NOTE]
> O suplemento de reunião Skype para Microsoft Office, que suporta o gerenciamento de reuniões de dentro do cliente de mensagens e colaboração do Outlook, instala automaticamente com Skype para clientes corporativos. 
  
> [!NOTE]
> O programa de instalação do Office 365 não desinstala versões anteriores do Lync. O Skype para Business client instala lado a lado com outros clientes do Lync. 
  
## <a name="installing-windows-clients"></a>Instalando clientes Windows

- [Personalizar a instalação de cliente do Windows no Skype para Business Server](customize-windows-client-installation.md)
    
- [Configure the client experience with Skype for Business](configure-the-client-experience.md)
    
- [Configurar lista de contatos Inteligente no Skype for Business Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Instalando clientes de dispositivos

- [Install and test Skype for Business for Windows Phone](windows-phone.md)
    
- [Install and test Skype for Business for iOS](ios.md)
    
    
- [Implantar o Lync VDI plug-in com Skype para Business Server](deploy-the-lync-vdi-plug-in.md)
    
- [Implantar clientes para download da Web no Skype para Business Server](deploy-web-downloadable-clients.md)
    
- [Personalizar a experiência do cliente Mac no Skype for Business](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Confira também

[Implantar o Skype para o cliente de negócios no Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
