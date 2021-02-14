---
title: Implantar clientes para o Skype for Business Server
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Resumo: Visão geral dos métodos de instalação do cliente corporativo para o Skype for Business.'
ms.openlocfilehash: ccaed5620c7f524a5a39fc6a35e6d688cd97a0eb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805691"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Implantar clientes para o Skype for Business Server
 
**Resumo:** Visão geral dos métodos de instalação do cliente corporativo para o Skype for Business.
  
A maneira como você implanta o Skype for Business para seus usuários depende se você comprou o Skype for Business como parte de um plano do Microsoft 365 ou Office 365 ou comprou uma versão licenciada por volume do Skype for Business. 
  
- **Microsoft 365 ou Office 365** Se você tiver um plano do Microsoft 365 ou Office 365 que inclua o Skype for Business, a tecnologia de instalação usada será chamada de Clique para Executar. Você pode permitir que seus usuários instalem o Skype for Business por conta própria no Centro de administração do Microsoft 365. Ou você pode implantar o Skype for Business para seus usuários baixando o software para sua rede local e, em seguida, usando suas ferramentas de implantação de software existentes, como com o Microsoft Endpoint Configuration Manager. Para obter informações de instalação sobre o Skype for Business que vem com o Microsoft 365 e o Office 365, confira Implantar o cliente Skype for Business no [Microsoft 365 ou Office 365.](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)
    
- **Licenciada por volume** Se você tiver uma versão licenciada por volume do cliente Skype for Business 2015 ou 2016, a tecnologia de instalação usada é o Windows Installer (MSI). Um pacote de instalação baseado no Windows Installer consiste em vários arquivos MSI. Um pacote de núcleo MSI de linguagem neutra é combinado com um ou mais pacotes de linguagem específica para fazer um produto completo. A instalação reúne os pacotes individuais e efetua a personalização e tarefas de manutenção durante e após a instalação do Office nos computadores dos usuários. O cliente Skype for Business 2019 usa instaladores Clique para Executar.
    
Os tópicos desta seção descrevem como usar e personalizar o Windows Installer para implantar o cliente do Skype for Business para seus usuários por meio de seus procedimentos normais.
  
> [!NOTE]
> O Complemento de Reunião do Skype para Microsoft Office, que oferece suporte ao gerenciamento de reuniões de dentro do cliente de colaboração e mensagens do Outlook, é instalado automaticamente com clientes do Skype for Business. 
  
> [!NOTE]
> Os programas de instalação do Microsoft 365 e office 365 não desinstalam versões anteriores do Lync. O cliente Skype for Business é instalado lado a lado com outros clientes do Lync. 
  
## <a name="installing-windows-clients"></a>Instalando clientes do Windows

- [Personalizar a instalação de cliente do Windows no Skype for Business Server](customize-windows-client-installation.md)
    
- [Configurar a experiência do cliente com o Skype for Business](configure-the-client-experience.md)
    
- [Configurar a lista de contatos Inteligente no Skype for Business Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Instalando clientes de dispositivo

- [Instalar e testar o Skype for Business para Windows Phone](windows-phone.md)
    
- [Instalar e testar o Skype for Business para iOS](ios.md)
    
    
- [Implantar o plug-in VDI do Lync com o Skype for Business Server](deploy-the-lync-vdi-plug-in.md)
    
- [Implantar clientes para download da Web no Skype for Business Server](deploy-web-downloadable-clients.md)
    
- [Personalizar a experiência de cliente do Mac no Skype for Business](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Confira também

[Implantar o cliente Skype for Business no Microsoft 365 ou Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
