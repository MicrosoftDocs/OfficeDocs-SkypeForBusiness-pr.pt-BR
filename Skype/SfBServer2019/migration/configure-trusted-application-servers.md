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
ms.localizationpriority: medium
description: Em um ambiente misto, se você criar um novo servidor de aplicativos confiável, deverá definir o pool de próximo salto como um pool de Skype for Business Server 2019. Em um ambiente misto, o pool herdado e o pool Skype for Business Server 2019 aparecem na lista lista listada. Selecionar o pool herdado não é suportado.
ms.openlocfilehash: 9965af757a570cfd787bb482a932d2817fd07ab0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58584465"
---
# <a name="configure-trusted-application-servers"></a>Configurar os servidores de aplicativos confiáveis

Em um ambiente misto, se você criar um novo servidor de aplicativos confiável, deverá definir o pool de próximo salto como um pool de Skype for Business Server 2019. Em um ambiente misto, o pool herdado e o pool Skype for Business Server 2019 aparecem na lista lista listada. Selecionar o pool herdado não é suportado.
  
> [!IMPORTANT]
> Se você estiver migrando um servidor de aplicativos confiável, também deverá atualizar a versão do UCMA que está usando. Se você criar um novo Pool de Aplicativos Confiáveis para Skype for Business Server 2019, atualize o UCMA para a versão incluída no Skype for Business Server 2019 ou na versão mais recente disponível. 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>Selecione Skype for Business Server 2019 como próximo salto ao criar um servidor de aplicativos confiáveis

1. Abra o Construtor de Topologia.
    
2. No painel esquerdo, clique com o botão direito do mouse em **Servidores de aplicativos confiáveis** e clique em **Novo Pool de Aplicativos Confiáveis.**
    
3. Insira o **FQDN do** pool de aplicativos confiáveis e selecione se ele será de servidor único ou de vários servidores. 
    
4. Clique em **Avançar**.
    
5. Na página **Selecionar o próximo salto,** na lista, selecione o pool de front-end Skype for Business Server 2019. 
    
6. Clique em **Concluir**.
    
7. Selecione o nó superior **Skype for Business Server** e, no menu **Ação,** selecione **Publicar**.
    
    Verifique se o **Pool de Aplicativos Confiáveis** foi criado com êxito e está associado ao pool de Front-End correto. 
    

