---
title: Configurar servidores de aplicativo confiáveis
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Em um ambiente misto, se você criar um novo servidor de aplicativos confiável, deverá definir o próximo pool de saltos como um pool do Skype for Business Server 2019. Em um ambiente misto, o pool herdado e o pool do Skype for Business Server 2019 aparecem na lista suspensa. Não há suporte para a seleção do pool herdado.
ms.openlocfilehash: a853065c8888ce9e160b34d182ec8bde6f4569f3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813769"
---
# <a name="configure-trusted-application-servers"></a>Configurar servidores de aplicativo confiáveis

Em um ambiente misto, se você criar um novo servidor de aplicativos confiável, deverá definir o próximo pool de saltos como um pool do Skype for Business Server 2019. Em um ambiente misto, o pool herdado e o pool do Skype for Business Server 2019 aparecem na lista suspensa. Não há suporte para a seleção do pool herdado.
  
> [!IMPORTANT]
> Se você estiver migrando um servidor de aplicativos confiável, também deverá atualizar a versão do UCMA que você está usando. Se você criar um novo pool de aplicativos confiável para o Skype for Business Server 2019, deverá atualizar o UCMA para a versão incluída com o Skype for Business Server 2019 ou a versão mais recente disponível. 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>Selecione o Skype for Business Server 2019 como próximo nó ao criar um servidor de aplicativos confiável

1. Abrir o construtor de topologias.
    
2. No painel esquerdo, clique com o botão direito do mouse em **servidores de aplicativos confiáveis** e clique em **novo pool de aplicativos confiáveis**.
    
3. Digite o **FQDN do pool** do pool de aplicativos confiável e selecione se ele será de servidor único ou de vários servidores. 
    
4. Click **Next**.
    
5. Na lista **selecionar o próximo salto** , na lista, selecione o pool de front-end do Skype for Business Server 2019. 
    
6. Clique em **Concluir**.
    
7. Selecione o nó superior **Skype for Business Server**e, no menu **ação** , selecione **publicar**.
    
    Verifique se o **pool de aplicativos confiável** foi criado com êxito e associado ao pool de front-end correto. 
    

