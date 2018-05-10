---
title: Implantar a ferramenta SEFAUtil no Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Implantando a ferramenta de SEFAUtil em Skype para Business Server.
ms.openlocfilehash: 4def73d0bca655569275f61d9ebfeafb4ab7e3d4
ms.sourcegitcommit: b394b394e6c51fe0d75b1eec47f6ada1b0265b63
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2018
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business-2015"></a>Implantar a ferramenta SEFAUtil no Skype for Business 2015
 
Implantando a ferramenta de SEFAUtil em Skype para Business Server.
  
Para implantar e gerenciar o atendimento de chamada de grupo, você precisará usar o Skype para Business Server versão da ferramenta SEFAUtil. 
  
> [!IMPORTANT]
> Tempo de execução do Microsoft Unified Communications Managed API (UCMA) 5 deve ser instalado em qualquer computador no qual você pretende executar a ferramenta SEFAUtil. Baixá-lo aqui: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=47344). Você também pode baixar o SDK do UCMA 5, que inclui o tempo de execução, aqui: [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).
  
Você pode executar a ferramenta de SEFAUtil em qualquer pool de Front-End em sua implantação. Para executar a ferramenta de SEFAUtil você deve executar as etapas 1, 2 e 3 do Skype para o Assistente de implantação de negócios no computador de aplicativos confiáveis. SEFAUtil requer o repositório de configuração local estar presentes, bem como um certificado.
  
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
    

