---
title: Implantar a ferramenta SEFAUtil no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Implantação da ferramenta SEFAUtil no Skype for Business Server.
ms.openlocfilehash: 20cda161c182c8dfb426f61b793366b7f60f37d5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812381"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Implantar a ferramenta SEFAUtil no Skype for Business
 
Implantação da ferramenta SEFAUtil no Skype for Business Server.
  
Para implantar e gerenciar o Atendimento de Chamadas em Grupo, você precisa usar a versão do Skype for Business Server da ferramenta SEFAUtil. 
  
> [!IMPORTANT]
> O Microsoft Unified Communications Managed API (UCMA) 5 Runtime deve ser instalado em qualquer computador em que você planeje executar a ferramenta SEFAUtil. Baixe-o aqui: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344). Você também pode baixar o UCMA 5 SDK, que inclui o tempo de execução, aqui: [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).
  
Você pode executar a ferramenta SEFAUtil em qualquer pool de Front-End em sua implantação. Para executar a ferramenta SEFAUtil, você deve executar as Etapas 1, 2 e 3 do Assistente de Implantação do Skype for Business no Computador de Aplicativo Confiável. A SEFAUtil exige que o armazenamento de configuração local seja presente, bem como um certificado.
  
> [!NOTE]
> Para obter mais detalhes sobre como executar a SEFAUtil, consulte o artigo do blog , "[Como obter SEFAutil em execução?](https://go.microsoft.com/fwlink/?LinkId=278940)". 
  
### <a name="to-deploy-sefautil"></a>Para implantar a SEFAUtil

1. Faça logoff no computador onde o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário **necessários,** conforme descrito em Delegate Setup Permissions .
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**
    
3. A ferramenta SEFAUtil pode ser executado somente em um computador que faz parte de um pool de aplicativos confiáveis. Se necessário, defina um pool de aplicativos confiáveis para o pool de Front-End onde você planeja executar SEFAUtil. Na linha de comando, execute:
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > FQDN do pool: O FQDN do servidor ou pool que hospedará o aplicativo SEFAUtil (geralmente um pool ou servidor front-end do Skype for Business).
    > FQDN do Registrador de Pool: O FQDN do servidor front-end do Skype for Business ou pool associado a este pool de aplicativos.
    > Site do Pool: A ID do Site do site no qual este pool está.

4. Defina a ferramenta SEFAUtil como um aplicativo confiável. Na linha de comando, execute:
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > Você pode usar uma porta diferente, se necessário. 
  
5. Habilita a topologia com suas alterações. Na linha de comando, execute:
    
   ```powershell
   Enable-CsTopology
   ```

6. Caso ainda não tenha feito isso, baixe a versão do [](https://www.microsoft.com/download/details.aspx?id=52631)Skype for Business Server da ferramenta SEFAUtil deste local e instale-a no pool de aplicativos confiáveis criado na etapa 3.
    
7. Verifique se a ferramenta SEFAUtil está sendo executado corretamente, da seguinte maneira: 
    
    a. Execute a ferramenta no prompt de comando do Windows com privilégios de administrador para exibir as configurações de encaminhamento de chamada de um usuário em sua implantação.
    
    b. Exibe as configurações de encaminhamento de chamada de um usuário. Na linha de comando, execute:
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

As configurações de encaminhamento de chamada do usuário serão exibidas.
    

