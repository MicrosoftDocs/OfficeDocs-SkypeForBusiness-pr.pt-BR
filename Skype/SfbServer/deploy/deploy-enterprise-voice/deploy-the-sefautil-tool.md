---
title: Implantar a ferramenta SEFAUtil no Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Implantando a ferramenta de SEFAUtil em Skype para Business Server.
ms.openlocfilehash: eba4c6d9c6d0c48256621537350a822c3314ca40
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business-2015"></a>Implantar a ferramenta SEFAUtil no Skype for Business 2015
 
Implantando a ferramenta de SEFAUtil em Skype para Business Server.
  
Para implantar e gerenciar o atendimento de chamada de grupo, você precisará usar o Skype para Business Server versão da ferramenta SEFAUtil. 
  
> [!IMPORTANT]
> O Microsoft UCMA (Unified Communications Managed API) 3.0 Core SDK deve estar instalado em qualquer computador no qual você planeja executar a ferramenta SEFAUtil. 
  
Você pode executar a ferramenta de SEFAUtil em qualquer pool de Front-End em sua implantação.
  
> [!NOTE]
> Para obter mais detalhes sobre como executar SEFAUtil, consulte o artigo do blog Technet "[como obter SEFAutil executando?](https://go.microsoft.com/fwlink/?LinkId=278940)". 
  
### <a name="to-deploy-sefautil"></a>Para implantar a SEFAUtil

1. Faça logon no computador onde o Skype do Shell de gerenciamento do servidor de negócios está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em **Delegate Setup Permissions**.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. A ferramenta SEFAUtil só pode ser executada em um computador que integra um pool de aplicativos confiáveis. Se necessário, definir um pool de aplicativos confiáveis para o pool de Front-End no qual você pretende executar SEFAUtil. Na linha de comando, execute:
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

4. Defina a ferramenta SEFAUtil como um aplicativo confiável. Na linha de comando, execute:
    
   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > Se necessário, você pode usar uma porta diferente. 
  
5. Habilite a topologia com suas alterações. Na linha de comando, digite:
    
  ```
  Enable-CsTopology
  ```

6. Se você ainda não estiver, baixe o Skype para Business Server versão da ferramenta SEFAUtil [nesse local](https://www.microsoft.com/en-us/download/details.aspx?id=52631)e instale-o em um pool de aplicativos confiáveis que você criou na etapa 3.
    
7. Verifique se a ferramenta SEFAUtil está sendo executada corretamente conforme segue: 
    
    a. Execute a ferramenta no prompt de comando do Windows com privilégios de administrador para exibir as configurações de encaminhamento de chamada de um usuário de sua implantação.
    
    b. Exiba as configurações de um usuário de encaminhamento de chamadas. Na linha de comando, execute:
    
  ```
  SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
  ```

As configurações de encaminhamento de chamada do usuário serão exibidas.
    

