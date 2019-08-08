---
title: Implantar a ferramenta SEFAUtil no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Implantando a ferramenta SEFAUtil no Skype for Business Server.
ms.openlocfilehash: 1721f4d611a08a3054366e36b0ec9a3ebccf6c78
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245386"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Implantar a ferramenta SEFAUtil no Skype for Business
 
Implantando a ferramenta SEFAUtil no Skype for Business Server.
  
Para implantar e gerenciar o recebimento de chamadas em grupo, você precisa usar a versão do Skype for Business Server da ferramenta SEFAUtil. 
  
> [!IMPORTANT]
> A API gerenciada de comunicação unificada da Microsoft (UCMA) 5 Runtime deve ser instalada em qualquer computador em que você planeja executar a ferramenta SEFAUtil. Baixe aqui: [comunicação unificada API gerenciada do tempo de execução 5,0](https://www.microsoft.com/en-us/download/details.aspx?id=47344). Você também pode baixar o SDK do UCMA 5, que inclui o tempo de execução, aqui: [UCMA 5,0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).
  
Você pode executar a ferramenta SEFAUtil em qualquer pool de front-ends na sua implantação. Para executar a ferramenta SEFAUtil, você deve executar as etapas 1, 2 e 3 do assistente de implantação do Skype for Business no computador do aplicativo confiável. O SEFAUtil exige que o repositório de configuração local esteja presente, bem como um certificado.
  
> [!NOTE]
> Para obter mais detalhes sobre como executar o SEFAUtil, confira o artigo "como fazer com[que SEFAUtil seja executado?](https://go.microsoft.com/fwlink/?LinkId=278940)". 
  
### <a name="to-deploy-sefautil"></a>Para implantar a SEFAUtil

1. Faça logon no computador em que o Shell de gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em **permissões de configuração do representante**.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. A ferramenta SEFAUtil só pode ser executada em um computador que integra um pool de aplicativos confiáveis. Se necessário, defina um pool de aplicativos confiável para o pool de front-ends em que você planeja executar o SEFAUtil. Na linha de comando, execute:
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > FQDN do pool: o FQDN do servidor ou pool que hospedará o aplicativo SEFAUtil (geralmente um servidor front-end do Skype for Business ou pool).
    > FQDN do registrador de pool: o FQDN do servidor de front-end do Skype for Business ou pool associado a este pool de aplicativos.
    > Site de pool: a ID do site na qual esse pool é hospedado.

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

6. Se ainda não fez isso, baixe a versão do Skype for Business Server da ferramenta SEFAUtil deste [local](https://www.microsoft.com/en-us/download/details.aspx?id=52631)e instale-a no pool de aplicativos confiável que você criou na etapa 3.
    
7. Verifique se a ferramenta SEFAUtil está sendo executada corretamente conforme segue: 
    
    a. Execute a ferramenta no prompt de comando do Windows com privilégios de administrador para exibir as configurações de encaminhamento de chamada de um usuário de sua implantação.
    
    b. Exibir as configurações de encaminhamento de chamadas de um usuário. Na linha de comando, execute:
    
   ```
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

As configurações de encaminhamento de chamada do usuário serão exibidas.
    

