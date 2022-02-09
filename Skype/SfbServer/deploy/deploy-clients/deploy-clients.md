---
title: Implantar clientes para Skype for Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Resumo: Visão geral dos métodos de instalação do cliente corporativo para Skype for Business.'
ms.openlocfilehash: 2e52de479b181e13be3124baeec0e76787b863a0
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399375"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Implantar clientes para Skype for Business Server
 
**Resumo:** Visão geral dos métodos de instalação do cliente corporativo para Skype for Business.
  
A implantação Skype for Business aos usuários depende se você comprou Skype for Business como parte de um plano Microsoft 365 ou Office 365 ou se comprou uma versão licenciada por volume do Skype for Business. 
  
- **Microsoft 365 ou Office 365** Se você tiver um plano Microsoft 365 ou Office 365 que inclua Skype for Business, a tecnologia de instalação usada será chamada de Clique para Executar. Você pode permitir que seus usuários instalem Skype for Business para si mesmos a partir do Centro de administração do Microsoft 365. Ou, você pode implantar Skype for Business para seus usuários baixando o software para sua rede local e usando suas ferramentas de implantação de software existentes, como com Microsoft Endpoint Configuration Manager. Para obter informações de instalação Skype for Business que vêm com Microsoft 365 e Office 365, consulte [Deploy the Skype for Business client in Microsoft 365 or Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).
    
- **Volume licenciado** Se você tiver uma versão licenciada por volume do cliente Skype for Business 2015 ou 2016, a tecnologia de instalação usada será Windows Installer (MSI). Um Windows de instalação baseado no Instalador consiste em vários arquivos MSI. Um pacote de núcleo MSI de linguagem neutra é combinado com um ou mais pacotes de linguagem específica para fazer um produto completo. A instalação reúne os pacotes individuais e efetua a personalização e tarefas de manutenção durante e após a instalação do Office nos computadores dos usuários. O Skype for Business cliente 2019 usa instaladores Clique para Executar.
    
Os tópicos desta seção descrevem como usar e personalizar o instalador Windows para implantar o cliente Skype for Business para seus usuários por meio de seus procedimentos normais.
  
> [!NOTE]
> O Reunião do Skype do Microsoft Office, que oferece suporte ao gerenciamento de reuniões de dentro do cliente de Outlook de mensagens e colaboração, é instalado automaticamente com Skype for Business clientes. 
  
> [!NOTE]
> Os Microsoft 365 e Office 365 de instalação não desinstalam versões anteriores do Lync. O Skype for Business cliente instala lado a lado com outros clientes do Lync. 
  
## <a name="installing-windows-clients"></a>Instalando Windows clientes

- [Personalizar Windows instalação do cliente no Skype for Business Server](customize-windows-client-installation.md)
    
- [Configurar a experiência do cliente com Skype for Business](configure-the-client-experience.md)
    
- [Configurar a lista de contatos inteligentes no Skype for Business Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Instalando clientes de dispositivo

- [Instalar e testar Skype for Business para Windows Phone](windows-phone.md)
    
- [Instalar e testar Skype for Business iOS](ios.md)
    
    
- [Implantar o plug-in VDI do Lync com Skype for Business Server](deploy-the-lync-vdi-plug-in.md)
    
- [Implantar clientes baixáveis da Web em Skype for Business Server](deploy-web-downloadable-clients.md)
    
- [Personalizar a experiência do cliente Mac no Skype for Business](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Confira também

[Implantar o Skype for Business cliente no Microsoft 365 ou Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
