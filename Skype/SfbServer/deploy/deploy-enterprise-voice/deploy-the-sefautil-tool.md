---
title: Implantar a ferramenta SEFAUtil no Skype for Business
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Implantando a ferramenta SEFAUtil no Skype for Business Server.
---

# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Implantar a ferramenta SEFAUtil no Skype for Business
 
Implantando a ferramenta SEFAUtil no Skype for Business Server.
  
Para implantar e gerenciar a Coleta de Chamada de Grupo, você precisa usar a versão Skype for Business Server da ferramenta SEFAUtil. 
  
> [!IMPORTANT]
> Microsoft Unified Communications Managed API (UCMA) 5 Runtime deve ser instalado em qualquer computador em que você planeja executar a ferramenta SEFAUtil. Baixe-o aqui: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344). Você também pode baixar o SDK UCMA 5, que inclui o tempo de execução, aqui: [SDK UCMA 5.0](https://www.microsoft.com/download/details.aspx?id=47345).
  
Você pode executar a ferramenta SEFAUtil em qualquer pool de Front-End em sua implantação. Para executar a ferramenta SEFAUtil, você deve executar as Etapas 1, 2 e 3 do Assistente de Implantação Skype for Business no Computador de Aplicativo Confiável. SEFAUtil exige que o armazenamento de configuração local seja presente, bem como um certificado.
  
> [!NOTE]
> Para obter mais detalhes sobre como executar o SEFAUtil, consulte o artigo do blog" "[Como obter SEFAutil em execução?](/archive/blogs/jenstr/how-to-get-sefautil-running)". 
  
### <a name="to-deploy-sefautil"></a>Para implantar SEFAUtil

1. Faça logoff no computador onde o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário **necessários**, conforme descrito em Permissões de Instalação do Representante.
    
2. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, em** Todos os **Programas, em** Skype for Business **2015** e em Skype for Business Server **Gerenciamento**.
    
3. A ferramenta SEFAUtil só pode ser executado em um computador que faz parte de um pool de aplicativos confiável. Se necessário, defina um pool de aplicativos confiáveis para o pool de Front-End onde você planeja executar SEFAUtil. Na linha de comando, execute:
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > FQDN do Pool: O FQDN do servidor ou pool que hospedará o aplicativo SEFAUtil (geralmente um servidor ou pool Skype for Business front-end).
    > FQDN do Registrador de Pool: O FQDN do servidor Skype for Business ou pool de front-end associado a esse pool de aplicativos.
    > Site do Pool: A ID do Site do site no qual esse pool está.

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

6. Se você ainda não tiver feito isso, baixe a versão Skype for Business Server da ferramenta SEFAUtil deste local e instale-a no pool de aplicativos confiáveis que você criou na etapa 3.[](https://www.microsoft.com/download/details.aspx?id=52631)
    
7. Verifique se a ferramenta SEFAUtil está sendo executado corretamente, da seguinte maneira: 
    
    a. Execute a ferramenta no prompt de Windows com privilégios de administrador para exibir as configurações de encaminhamento de chamada de um usuário em sua implantação.
    
    b. Exibe as configurações de encaminhamento de chamada de um usuário. Na linha de comando, execute:
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

As configurações de encaminhamento de chamada para o usuário serão exibidas.
