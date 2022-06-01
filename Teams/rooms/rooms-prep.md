---
title: Preparar seu ambiente
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: Saiba mais sobre como preparar sua infraestrutura para implantar Salas do Microsoft Teams para que você possa aproveitar todos os recursos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0bedb70ade23f92424a14e4bea3f1462fc2cbccf
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823050"
---
# <a name="prepare-your-environment"></a>Preparar seu ambiente

Esta seção contém uma visão geral das etapas necessárias para preparar seu ambiente para que você possa usar todos os recursos do Salas do Microsoft Teams.
  
1. Prepare uma conta de recurso para cada Salas do Microsoft Teams console. Consulte [Implantar Salas do Microsoft Teams](rooms-deploy.md) para obter detalhes.
    
2. Verifique se existe uma conexão de rede/Internet para o dispositivo usar. 
  
3. Para aprimorar sua experiência, a Microsoft coleta dados. Para permitir que a Microsoft colete dados, permita estes sites:

   - Ponto de extremidade do cliente de telemetria: `https://vortex.data.microsoft.com/`
   - Ponto de extremidade de configurações de telemetria:` https://settings.data.microsoft.com/`
    
### <a name="create-and-test-a-resource-account"></a>Criar e testar uma conta de recurso

Uma *conta de* recurso é uma conta que o cliente Salas do Microsoft Teams usa para acessar recursos do Exchange, como calendário, e para se conectar ao Microsoft Teams. Consulte [Implantar Salas do Microsoft Teams](rooms-deploy.md) para obter detalhes.
  
### <a name="check-network-availability"></a>Verificar a disponibilidade da rede

Para funcionar corretamente, Salas do Microsoft Teams deve ter acesso a uma rede com fio que atenda a estes requisitos:
  
- Acesso à sua instância do Active Directory Azure Active Directory (Azure AD), bem como ao Microsoft Exchange e Microsoft Teams.

- Acesso a um servidor que pode fornecer um endereço IP usando DHCP. Salas do Microsoft Teams pode ser configurado com um endereço IP estático na primeira inicialização da unidade.

- Acessar as portas HTTP 80 e 443.

- Portas TCP e UDP configuradas conforme descrito nos [](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) requisitos de porta e protocolo para servidores para implementações de Skype for Business Server locais ou [URLs e intervalos](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) de endereços IP Office 365 e Microsoft 365 e Office 365 para Microsoft Teams.

Se sua rede é executada através de um proxy, você também precisa do endereço de proxy ou de informações do script.
    
> [!IMPORTANT]
> Salas do Microsoft Teams não dá suporte à autenticação de proxy, pois ela pode interferir nas operações regulares da sala. Verifique se Salas do Microsoft Teams foram isentos da autenticação de proxy antes de entrar em produção.

> [!IMPORTANT]
> Use uma conexão de rede de 1 Gbps com fio para assegurar a largura de banda necessária. 

> [!NOTE]
> As atualizações de software Salas do Microsoft Teams são baixadas automaticamente do Microsoft Store para Empresas. Consulte [Os pré-requisitos para Microsoft Store para Empresas e Education](/microsoft-store/prerequisites-microsoft-store-for-business) para verificar se o console da sala será capaz de acessar a loja e atualizar automaticamente.
  
### <a name="certificates"></a>Certificados

Seu Salas do Microsoft Teams dispositivo usa certificados para Exchange Web Services, Microsoft Teams ou Skype for Business, uso de rede e autenticação. Se os servidores relacionados usarem certificados públicos, que é o caso de implantações online e locais, não deverá haver nenhuma ação adicional necessária por parte do administrador para instalar certificados. Se, por outro lado, a autoridade de certificação for uma AC privada, o dispositivo precisará confiar nessa AC. Isso significa ter os certificados de cadeia de AC + AC instalados no dispositivo. Com a adição do dispositivo ao domínio, será possível executar essa tarefa automaticamente.
  
Você instalará os certificados da mesma forma como faria para qualquer outro cliente Windows. 

> [!IMPORTANT]
> Se o servidor proxy utilizar certificados assinados internamente, você deverá instalar a cadeia de certificados interna, incluindo a AC raiz, no Salas do Microsoft Teams dispositivo.
  
> [!NOTE]
> Os certificados podem ser necessários para que os Salas do Microsoft Teams usem Skype for Business Server.
  
### <a name="proxy"></a>Proxy

Salas do Microsoft Teams é projetado para herdar as configurações de proxy do Windows sistema operacional. Acesse o Windows sistema operacional da seguinte maneira:
  
1. Na interface do usuário Salas do Microsoft Teams, clique no ícone de engrenagem Configurações em que você será solicitado a fornecer a senha de Administrador local no dispositivo (a senha padrão é **sfb**).
2. Toque em **Configurações** seguido de tocar no botão Ir para **Windows** e, em seguida, tocar no botão Ir para entrar no **Administração** e, em seguida, clicar no botão Administrador (se o computador  estiver ingressado no domínio, escolha Outro Usuário **e** use .\admin como o nome de usuário).
3. Na caixa **Pesquisar Windows** inferior esquerda, digite regedit (pressione a tela ou clique com o botão direito do mouse e escolha Executar **como administrador**).
4. Clique na pasta HKEY_USERS (você verá uma lista de SIDs de usuários do computador) e verifique se a pasta raiz HKEY_USERS está selecionada.
       
5. Clique em Arquivo e escolha **Carregar Hive.**
6. Navegue até **a pasta C:\Users\Skype** e digite na caixa Nome do arquivo NTUSER.dat e pressione o botão Abrir

7. Você será solicitado a fornecer um nome de chave para o Hive recém-carregado; digite Skype (agora você deve ver as configurações do Registro para o Skype Usuário).
 
8. Abra a Skype e navegue até HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings e verifique se essas configurações foram inseridas: 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    Se ProxyServer não existir, talvez seja necessário adicionar essa chave como uma cadeia de caracteres. Altere xx.xx.xx.xx:8080 para o ip/host e a porta de seu servidor proxy.
 
    Se o cliente estiver usando um arquivo PAC, a configuração será semelhante ao exemplo abaixo:

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. Ao concluir suas alterações, realce a chave do Usuário do Skype (pasta raiz do Skype) e opte por descarregar o Hive do menu de arquivos do Registro (será solicitada sua confirmação; selecione **Sim**).
    
10. Agora, você pode fechar o editor do Registro e digitar logoff na caixa de pesquisa do Windows.
    
11. Voltando à tela de entrada, escolha o usuário **Skype**. Se todas as etapas anteriores foram bem-sucedidas, o Salas do Microsoft Teams dispositivo será conectado com êxito.
    
Consulte o [artigo segurança de](./security.md#network-security) rede para obter detalhes completos sobre FQDNs, portas e intervalos de endereços IP necessários para Salas do Microsoft Teams.
  
### <a name="admin-group-management"></a>Gerenciamento de grupo de administradores

Se você optar por ingressar em um domínio (Azure Active Directory ou Active Directory), poderá usar o Microsoft Endpoint Manager, o Política de Grupo ou o Gerenciamento de Computador Local para definir um Grupo de Segurança como administrador local, assim como faria para um computador Windows em seu domínio. Qualquer membro desse grupo de segurança pode inserir as respectivas credenciais e desbloquear as configurações.
  
> [!NOTE]
> Se seu dispositivo de Salas do Microsoft Teams perder confiabilidade com o domínio (por exemplo, se você remover as Salas do Microsoft Teams do domínio após terem sido agregadas a ele), você não poderá autenticar esse dispositivo e abrir Configurações. A solução é fazer logon com a conta de Administrador local. 
  
## <a name="local-accounts"></a>Contas locais

### <a name="microsoft-teams-rooms-local-user-account"></a>Salas do Microsoft Teams de usuário local

Salas do Teams inclui uma conta local sem senha chamada "Skype". Essa conta é usada para entrar no Windows iniciar o Salas do Teams aplicativo. Não há suporte para aplicar uma senha a essa conta. Consulte [Salas do Microsoft Teams Segurança](security.md) para obter mais informações.
  
### <a name="admin---local-administrator-account"></a>"Administrador" - Conta do Administrador Local

Salas do Microsoft Teams senha padrão é definida como "sfb". A senha pode ser alterada localmente por meio do modo Administração ou no arquivo AutoUnattend.xml (use o gerenciador de imagens do sistema do Windows do ADK para fazer a alteração no arquivo xml).
  
> [!CAUTION]
> Altere a senha Salas do Microsoft Teams logo que possível. 
  
A senha do Administrador local não é incluída como opção durante a Instalação.

Você pode ler mais sobre a Administração no artigo [Salas do Microsoft Teams Segurança](security.md).
  
### <a name="machine-account"></a>Conta do computador

Assim como qualquer Windows,  \> o nome do computador pode ser renomeado clicando com o botão direito do mouse Configurações **Sobre** \> **Renomear COMPUTADOR**.
  
Se você quiser renomear o computador depois de ingressá-lo em um domínio, use [Renomear Computador](/powershell/module/microsoft.powershell.management/rename-computer), um comando do PowerShell, seguido pelo novo nome do computador.
  
## <a name="related-topics"></a>Tópicos relacionados

[Planejar Salas do Microsoft Teams](rooms-plan.md)

[Requisitos das Salas do Microsoft Teams](requirements.md)
  
[Implantar Salas do Microsoft Teams](rooms-deploy.md)
  
[Configurar um console de Salas do Microsoft Teams](console.md)
  
[Gerenciar Salas do Microsoft Teams](rooms-manage.md)

[Pré-requisitos para Microsoft Store para Empresas e Educação](/microsoft-store/prerequisites-microsoft-store-for-business)
