---
title: Configurar servidores de aplicativo confiáveis
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Em um ambiente misto, se você criar um novo servidor de aplicativos confiáveis, você deve definir o pool do próximo salto para ser um Skype para Business Server 2019 pool. Em um ambiente misto, tanto o pool herdado e o Skype para Business Server 2019 pool aparecem na lista suspensa. Não há suporte para selecionar o pool herdado.
ms.openlocfilehash: 79f4de527008d2d9bf295fcb82eee433d04a1691
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890885"
---
# <a name="configure-trusted-application-servers"></a>Configurar servidores de aplicativo confiáveis

Em um ambiente misto, se você criar um novo servidor de aplicativos confiáveis, você deve definir o pool do próximo salto para ser um Skype para Business Server 2019 pool. Em um ambiente misto, tanto o pool herdado e o Skype para Business Server 2019 pool aparecem na lista suspensa. Não há suporte para selecionar o pool herdado.
  
> [!IMPORTANT]
> Se você estiver migrando o servidor de aplicativo confiável, você também deverá atualizar a versão do UCMA que você está usando. Se você criar um novo Pool de aplicativos confiáveis para Skype for Business Server 2019, você deverá atualizar UCMA para a versão incluída Skype para Business Server 2019 ou a versão mais recente disponível. 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>Selecione Skype para Business Server 2019 como próximo salto ao criar um servidor de aplicativos confiáveis

1. Abra o construtor de topologia.
    
2. No painel esquerdo, clique com o botão **servidores de aplicativos confiáveis** e clique em **Novo Pool de aplicativos confiáveis**.
    
3. Insira o **FQDN do Pool** do pool de aplicativos confiáveis e selecione se será servidor único ou vários servidores. 
    
4. Click **Next**.
    
5. Na página **Selecionar o próximo salto** , na lista, selecione o Skype para pool de negócios 2019 Front-End Server. 
    
6. Clique em **Concluir**.
    
7. Selecione o nó superior **Skype para Business Server**e, no menu **ação** , selecione **Publicar**.
    
    Verifique se o **Pool de aplicativos confiáveis** foi criado com êxito e associado ao pool de Front-End correto. 
    

