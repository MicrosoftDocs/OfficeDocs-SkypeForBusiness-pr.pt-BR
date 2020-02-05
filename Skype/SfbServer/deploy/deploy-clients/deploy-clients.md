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
description: 'Resumo: visão geral dos métodos de instalação do cliente corporativo para o Skype for Business.'
ms.openlocfilehash: 0e7859fe207ed80aa7dceef794aa57d15cc0c79b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768724"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Implantar clientes para o Skype for Business Server
 
**Resumo:** Visão geral dos métodos de instalação do cliente Enterprise para o Skype for Business.
  
A maneira como você implanta o Skype for Business para seus usuários depende se você comprou o Skype for Business como parte de um plano do Office 365 ou se comprou uma versão licenciada de volume do Skype for Business. 
  
- **Office 365** Se você tiver um plano do Office 365 que inclua o Skype for Business, a tecnologia de instalação que é usada é chamada de clique para executar. Com o Office 365, você pode permitir que os usuários instalem o Skype for Business por conta própria no portal do Office 365. Ou você pode implantar o Skype for Business para seus usuários baixando o software para a sua rede local e, em seguida, usando as ferramentas de implantação de software existentes, como o Gerenciador de configuração do Microsoft Endpoint. Para obter informações de instalação sobre o Skype for Business que vem com o Office 365, consulte [implantar o cliente Skype for Business no Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).
    
- **Volume licenciado** Se você tiver uma versão licenciada de volume do cliente Skype for Business 2015 ou 2016, a tecnologia de instalação usada pelo Windows Installer (MSI). Um pacote de instalação baseado no Windows Installer consiste em vários arquivos MSI. Um pacote de núcleo MSI de linguagem neutra é combinado com um ou mais pacotes de linguagem específica para fazer um produto completo. A instalação reúne os pacotes individuais e efetua a personalização e tarefas de manutenção durante e após a instalação do Office nos computadores dos usuários. O cliente Skype for Business 2019 usa instaladores com Clique para executar.
    
Os tópicos desta seção descrevem como usar e personalizar o Windows Installer para implantar o cliente Skype for Business para seus usuários por meio de seus procedimentos normais.
  
> [!NOTE]
> O suplemento de reunião do Skype para Microsoft Office, que dá suporte ao gerenciamento de reuniões dentro do cliente de mensagens e colaboração do Outlook, é instalado automaticamente com os clientes do Skype for Business. 
  
> [!NOTE]
> O programa de instalação do Office 365 não desinstala versões anteriores do Lync. O cliente Skype for Business é instalado lado a lado com outros clientes do Lync. 
  
## <a name="installing-windows-clients"></a>Instalar clientes do Windows

- [Personalizar a instalação do Windows Client no Skype for Business Server](customize-windows-client-installation.md)
    
- [Configure the client experience with Skype for Business](configure-the-client-experience.md)
    
- [Configurar lista de contatos Inteligente no Skype for Business Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Instalar clientes de dispositivos

- [Install and test Skype for Business for Windows Phone](windows-phone.md)
    
- [Install and test Skype for Business for iOS](ios.md)
    
    
- [Implantar o plug-in VDI do Lync com o Skype for Business Server](deploy-the-lync-vdi-plug-in.md)
    
- [Implantar clientes para download da Web no Skype for Business Server](deploy-web-downloadable-clients.md)
    
- [Personalizar a experiência do cliente Mac no Skype for Business](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Confira também

[Implantar o cliente Skype for Business no Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
