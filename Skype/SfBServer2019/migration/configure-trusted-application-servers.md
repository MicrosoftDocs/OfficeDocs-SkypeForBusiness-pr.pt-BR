---
title: Configurar os servidores de aplicativos confiáveis
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Em um ambiente misto, se você criar um novo servidor de aplicativos confiáveis, deverá definir o pool do próximo salto para ser um pool do Skype for Business Server 2019. Em um ambiente misto, o pool herdado e o pool do Skype for Business Server 2019 aparecem na lista de lista. Selecionar o pool herdado não é suportado.
ms.openlocfilehash: 1c0aac1efa4f83a81ccf2f3bb5ecbc925ee58839
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753941"
---
# <a name="configure-trusted-application-servers"></a>Configurar os servidores de aplicativos confiáveis

Em um ambiente misto, se você criar um novo servidor de aplicativos confiáveis, deverá definir o pool do próximo salto para ser um pool do Skype for Business Server 2019. Em um ambiente misto, o pool herdado e o pool do Skype for Business Server 2019 aparecem na lista de lista. Selecionar o pool herdado não é suportado.
  
> [!IMPORTANT]
> Se você estiver migrando um servidor de aplicativos confiáveis, também deverá atualizar a versão do UCMA que está usando. Se você criar um novo Pool de Aplicativos Confiáveis para o Skype for Business Server 2019, atualize o UCMA para a versão incluída no Skype for Business Server 2019 ou na versão mais recente disponível. 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>Selecione o Skype for Business Server 2019 como próximo salto ao criar um servidor de aplicativos confiáveis

1. Abra o Construtor de Topologia.
    
2. No painel esquerdo, clique com o botão direito do mouse em **Servidores de aplicativos** confiáveis e clique em **Novo Pool de Aplicativos Confiáveis.**
    
3. Insira o **FQDN do** Pool do pool de aplicativos confiáveis e selecione se ele será de servidor único ou de vários servidores. 
    
4. Clique em **Avançar**.
    
5. Na página **Selecionar o próximo salto,** na lista, selecione o pool de front-end do Skype for Business Server 2019. 
    
6. Clique em **Concluir**.
    
7. Selecione o nó superior **Skype for Business Server** e, no menu **Ação,** selecione **Publicar**.
    
    Verifique se o **Pool de Aplicativos** Confiáveis foi criado com êxito e se está associado ao pool de Front-End correto. 
    

