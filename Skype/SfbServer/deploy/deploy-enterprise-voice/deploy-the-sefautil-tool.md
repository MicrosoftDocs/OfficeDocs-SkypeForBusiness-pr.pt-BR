---
title: Implantar a ferramenta SEFAUtil no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Implantar a ferramenta SEFAUtil no Skype for Business Server.
ms.openlocfilehash: 306e2ec305e9e12cd3486691b3e239e2aedfb548
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41986806"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Implantar a ferramenta SEFAUtil no Skype for Business
 
Implantar a ferramenta SEFAUtil no Skype for Business Server.
  
Para implantar e gerenciar o recebimento de chamadas em grupo, você precisa usar a versão do Skype for Business Server da ferramenta SEFAUtil. 
  
> [!IMPORTANT]
> O Microsoft Unified Communications Managed API (UCMA) 5 Runtime deve ser instalado em qualquer computador no qual você planeja executar a ferramenta SEFAUtil. Baixe-o aqui: [Unified Communications Managed API 5,0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344). Você também pode baixar o UCMA 5 SDK, que inclui o tempo de execução, aqui: [UCMA 5,0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).
  
Você pode executar a ferramenta SEFAUtil em qualquer pool de front-ends em sua implantação. Para executar a ferramenta SEFAUtil você deve executar as etapas 1, 2 e 3 do assistente de implantação do Skype for Business no computador de aplicativo confiável. O SEFAUtil exige que o repositório de configuração local esteja presente, bem como um certificado.
  
> [!NOTE]
> Para obter mais detalhes sobre a execução do SEFAUtil, consulte o artigo do blog, "[How to Get SEFAUtil running?](https://go.microsoft.com/fwlink/?LinkId=278940)". 
  
### <a name="to-deploy-sefautil"></a>Para implantar o SEFAUtil

1. Faça logon no computador onde o Shell de gerenciamento do Skype for Business Server está instalado como um membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em **delegar permissões de configuração**.
    
2. Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, em **Skype for Business 2015**e em **Shell de gerenciamento do Skype for Business Server**.
    
3. A ferramenta SEFAUtil pode ser executada apenas em um computador que faça parte de um pool de aplicativos confiáveis. Se necessário, defina um pool de aplicativos confiáveis para o pool de front-ends onde você planeja executar o SEFAUtil. Na linha de comando, execute:
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > FQDN do pool: o FQDN do servidor ou pool que hospedará o aplicativo SEFAUtil (geralmente um servidor front-end do Skype for Business ou pool).
    > FQDN do registrador de pool: o FQDN do servidor front-end do Skype for Business ou pool associado a esse pool de aplicativos.
    > Site do pool: a ID do site em que este pool está hospedado.

4. Defina a ferramenta SEFAUtil como um aplicativo confiável. Na linha de comando, execute:
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > Você pode usar uma porta diferente, se necessário. 
  
5. Habilite a topologia com suas alterações. Na linha de comando, execute:
    
   ```powershell
   Enable-CsTopology
   ```

6. Se ainda não tiver feito isso, baixe a versão do Skype for Business Server da ferramenta SEFAUtil desse [local](https://www.microsoft.com/download/details.aspx?id=52631)e instale-a no pool de aplicativos confiáveis que você criou na etapa 3.
    
7. Verifique se a ferramenta SEFAUtil está funcionando corretamente, da seguinte maneira: 
    
    a. Execute a ferramenta a partir do prompt de comando do Windows com privilégios de administrador para exibir as configurações de encaminhamento de chamadas de um usuário em sua implantação.
    
    b. Exibir as configurações de encaminhamento de chamadas de um usuário. Na linha de comando, execute:
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

As configurações de encaminhamento de chamadas para o usuário serão exibidas.
    

