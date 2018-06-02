---
title: Implantar clientes do Skype for Business Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Resumo: Visão geral dos métodos de instalação de cliente enterprise para Skype para negócios.'
ms.openlocfilehash: 4c1253613befd5bf71add33b7ab9cab826d4a490
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2018
ms.locfileid: "19546466"
---
# <a name="deploy-clients-for-skype-for-business-server-2015"></a>Implantar clientes do Skype for Business Server 2015
 
**Resumo:** Visão geral dos métodos de instalação de cliente enterprise para Skype para negócios.
  
Como você implanta Skype for Business para seus usuários depende se você comprou Skype para negócios como parte de um plano do Office 365 ou você comprou uma versão licenciada do volume do Skype para negócios. 
  
- **Office 365** Se você tiver um plano do Office 365 que inclui Skype para a empresa, a tecnologia de instalação que é usada é chamada Click-to-Run. Com o Office 365, você pode permitir que os usuários instalar Skype for Business para si próprios do portal do Office 365. Ou então, você pode implantar Skype for Business para seus usuários baixando o software em sua rede local e, em seguida, usando suas ferramentas de implantação de software existentes, tais como com o Microsoft System Center Configuration Manager. Para obter informações de instalação sobre Skype for Business que vem com o Office 365, consulte [Deploy a Skype para o cliente de negócios no Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).
    
- **Licença de volume** Se você tiver uma versão de licença de volume do Skype para a empresa, a tecnologia de instalação que é usada é o Windows Installer (MSI). Um pacote de instalação baseada no Windows Installer consiste em vários arquivos MSI. Um pacote de núcleo MSI de linguagem neutra é combinado com um ou mais pacotes de linguagem específica para fazer um produto completo. A instalação reúne os pacotes individuais e efetua a personalização e tarefas de manutenção durante e após a instalação do Office nos computadores dos usuários.
    
Os tópicos desta seção descrevem como usar e personalizar o Windows Installer para implantar o Skype para o cliente de negócios para seus usuários por meio de seus procedimentos normais.
  
> [!NOTE]
> O Online meeting Add-in para Skype para os negócios, que suporta o gerenciamento de dentro do Outlook de reuniões cliente de mensagens e colaboração, instala automaticamente com o Skype para negócios. 
  
> [!NOTE]
> O programa de instalação do Office 365 não desinstala versões anteriores do Lync ou Office Communicator. O Skype para Business client instala lado a lado com outros clientes do Lync ou Office Communicator. 
  
## <a name="installing-windows-clients"></a>Instalando clientes Windows

- [Personalizar a instalação de cliente do Windows no Skype para Business Server 2015](customize-windows-client-installation.md)
    
- [Configurar a experiência do cliente com Skype para negócios](configure-the-client-experience.md)
    
- [Configurar a lista de contatos inteligente no Skype para Business Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Instalando clientes de dispositivos

- [Instalar e testar o Skype para Business para Windows Phone](windows-phone.md)
    
- [Instalar e testar o Skype for Business para iOS](ios.md)
    
- [Implantar o sistema de sala Skype no Skype para Business Server](deploy-skype-room-system.md)
    
- [Implantar Skype sala v2 de sistemas](room-systems-v2.md)
    
- [Implantar o Lync VDI plug-in com Skype para Business Server 2015](deploy-the-lync-vdi-plug-in.md)
    
- [Implantar clientes para download da Web no Skype para Business Server 2015](deploy-web-downloadable-clients.md)
    
- [Personalizar a experiência do cliente do Mac no Skype para negócios](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Consulte também

[Implantar o Skype para o cliente de negócios no Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)