---
title: Preparar seu Ambiente
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
description: Saiba mais sobre como preparar sua infraestrutura para a implantação Salas do Microsoft Teams para que você possa tirar proveito de todos os recursos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5003bbb3554436ca388990aeebfec4ce6dfb9f57
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58577955"
---
# <a name="prepare-your-environment"></a>Preparar seu ambiente

Esta seção contém uma visão geral das etapas necessárias para preparar seu ambiente para que você possa usar todos os recursos de Salas do Microsoft Teams.
  
1. Preparar uma conta de dispositivo para cada Salas do Microsoft Teams console. Consulte [Deploy Salas do Microsoft Teams](rooms-deploy.md) para obter detalhes.
    
2. Verifique se existe uma conexão de rede/Internet para o dispositivo usar.  
    
   Ele deve ser capaz de receber um endereço IP usando DHCP. (Salas do Microsoft Teams pode ser configurado com um endereço IP estático na primeira inicialização da unidade, mas, posteriormente, um endereço IP estático para o dispositivo pode ser configurado no dispositivo ou no comutamento upstream ou roteador.)

   Ele deve ter essas portas abertas (além de abrir as portas normais para mídia):
   - HTTPS: 443
   - HTTP: 80

   Se sua rede é executada através de um proxy, você também precisa do endereço de proxy ou de informações do script.
    
   > [!IMPORTANT]
   > Salas do Microsoft Teams não dá suporte à autenticação de proxy, pois pode interferir nas operações regulares da sala. Verifique se Salas do Microsoft Teams foram isentos da autenticação de proxy antes de entrar em produção.
  
3. Para aprimorar sua experiência, a Microsoft coleta dados. Para permitir que a Microsoft colete dados, permita estes sites:

   - Ponto de extremidade do cliente de telemetria: https://vortex.data.microsoft.com/
   - Ponto de extremidade das configurações de telemetria: https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>Criar e testar uma conta de dispositivo

Uma *conta de dispositivo* é uma conta que o cliente Salas do Microsoft Teams usa para acessar recursos de Exchange, como calendário, e para habilitar Skype for Business. Consulte [Deploy Salas do Microsoft Teams](rooms-deploy.md) para obter detalhes.
  
### <a name="check-network-availability"></a>Verificar a disponibilidade da rede

Para funcionar corretamente, o dispositivo Salas do Microsoft Teams deve ter acesso a uma rede com fio que atenda a esses requisitos:
  
- Acessar a instância do Active Directory ou do Azure Active Directory (Azure AD), bem como o servidores Microsoft Exchange e Skype for Business.

- Acesso a um servidor que pode fornecer um endereço IP usando DHCP. Salas do Microsoft Teams pode ser configurado com um endereço IP estático na primeira inicialização da unidade.

- Acessar as portas HTTP 80 e 443.

- Portas TCP e UDP configuradas conforme descrito em Requisitos de porta e protocolo para servidores para implementações de Skype for Business Server locais, ou [URLs](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) e intervalos de endereços IP do Microsoft 365 e Office 365 para implementações Microsoft Teams ou Skype for Business online. [](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols)

> [!IMPORTANT]
> Use uma conexão de rede de 1 Gbps com fio para assegurar a largura de banda necessária. 

> [!NOTE]
> As atualizações de software Salas do Microsoft Teams são baixadas automaticamente do Microsoft Store para Empresas. Consulte [Pré-requisitos para Microsoft Store para Empresas e Education](/microsoft-store/prerequisites-microsoft-store-for-business) para verificar se o console de sala será capaz de acessar a loja e a atualização automática.
  
### <a name="certificates"></a>Certificados

Seu Salas do Microsoft Teams usa certificados para serviços Web Exchange Web, Microsoft Teams ou Skype for Business, uso de rede e autenticação. Se os servidores relacionados usarem certificados públicos, o que ocorre com as implantações online e com algumas implantações locais, o administrador não precisará realizar nenhuma ação adicional para instalar os certificados. Por outro lado, se a autoridade de certificação for uma AC privada (típica em implantações locais), o dispositivo deverá confiar na AC, o que significa ter a AC e a cadeia de certificados de AC instaladas no dispositivo. Com a adição do dispositivo ao domínio, será possível executar essa tarefa automaticamente.
  
Você instalará os certificados da mesma forma como faria para qualquer outro cliente Windows.  
  
> [!NOTE]
> Os certificados podem ser necessários para que Salas do Microsoft Teams usar Skype for Business Server.
  
### <a name="proxy"></a>Proxy

Salas do Microsoft Teams foi projetado para herdar configurações de Proxy do sistema operacional Windows. Acesse o Windows sistema operacional da seguinte maneira:
  
1. Na interface do usuário Salas do Microsoft Teams, clique no ícone de engrenagem Configurações onde você será solicitado a solicitar a senha local do Administrador no dispositivo (a senha padrão é **sfb**).
2. Toque em **Configurações** seguido de tocar no botão **Ir** para Windows e  tocar no botão ir para  Administrador Entrar e clicar no botão Administrador (se o computador estiver ingressado no domínio, escolha Outro Usuário **e** use .\admin como o nome do usuário).
3. Na caixa **Pesquisar Windows** inferior à esquerda no regedit (pressione a tela ou clique com o botão direito do mouse e escolha Executar **como administrador**).
4. Clique na pasta HKEY_USERS (você verá uma lista de SIDs de usuários do computador) e verifique se a pasta raiz HKEY_USERS está selecionada.
       
5. Clique em Arquivo e escolha **Carregar Hive.**
6. Navegue até **a pasta C:\Users\Skype** digite na caixa Nome do arquivo NTUSER.dat e pressione o botão abrir

7. Você será solicitado a ter um nome de chave para seu Hive recém-carregado; digite em Skype (agora você deve ver as configurações do Registro para o Skype Usuário).
 
8. Abra a Skype chave e navegue até HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings certifique-se de que essas configurações sejam inseridas: 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    Se ProxyServer não existir, talvez seja necessário adicionar essa chave como uma cadeia de caracteres. Altere xx.xx.xx.xx:8080 para o ip/host e a porta de seu servidor proxy.
 
    Se o cliente estiver usando um arquivo PAC, a configuração se pareceria com o exemplo abaixo:

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. Ao concluir suas alterações, realce a chave do Usuário do Skype (pasta raiz do Skype) e opte por descarregar o Hive do menu de arquivos do Registro (será solicitada sua confirmação; selecione **Sim**).
    
10. Agora, você pode fechar o editor do Registro e digitar logoff na caixa de pesquisa do Windows.
    
11. Voltando à tela de entrada, escolha o usuário **Skype**. Se todas as etapas anteriores foram bem-sucedidas, o Salas do Microsoft Teams dispositivo Salas do Microsoft Teams entrará com êxito.
    
Consulte o [artigo segurança](./security.md#network-security) de rede para obter detalhes completos sobre FQDNs, portas e intervalos de endereços IP necessários para Salas do Microsoft Teams.
  
  
### <a name="create-provisioning-packages"></a>Criar pacotes de provisionamento

Você usará pacotes de provisionamento para autenticar para Exchange Server, Microsoft 365 ou Office 365.
  
### <a name="admin-group-management"></a>Gerenciamento de grupo de administradores

Após o ingresso no domínio, você pode usar a Política de Grupo ou o Gerenciamento de Computador Local para definir um Grupo de Segurança como administrador local, da mesma forma como faria com um computador Windows em seu domínio. Qualquer membro desse grupo de segurança pode inserir as respectivas credenciais e desbloquear as configurações.
  
> [!NOTE]
> Se seu dispositivo de Salas do Microsoft Teams perder confiabilidade com o domínio (por exemplo, se você remover as Salas do Microsoft Teams do domínio após terem sido agregadas a ele), você não poderá autenticar esse dispositivo e abrir Configurações. A solução é fazer logon com a conta de Administrador local. 
  
## <a name="local-accounts"></a>Contas locais

### <a name="microsoft-teams-rooms-local-user-account"></a>Salas do Microsoft Teams Conta de usuário local

A Conta de Dispositivo normalmente não usa senha. É possível atribuir a ela uma senha, mas há consequências, inclusive a possibilidade de o usuário ser bloqueado e não poder usar o aplicativo de console quando a senha expirar. Portanto, o administrador deve tomar cuidado para a senha não expirar.
  
### <a name="admin---local-administrator-account"></a>"Administrador" - Conta do Administrador Local

Salas do Microsoft Teams senha padrão é definida como "sfb". A senha pode ser alterada localmente indo para ir para Windows Configurações Ir para Windows ou no arquivo AutoUnattend.xml (use o gerenciador Windows System Image do ADK para fazer a alteração no arquivo \> xml).
  
> [!CAUTION]
> Certifique-se de alterar Salas do Microsoft Teams senha assim que possível. 
  
A senha do Administrador Local também pode ser gerenciada por meio da configuração de uma política de grupo em que os administradores do domínio se tornam administradores locais.
  
A senha do Administrador local não é incluída como opção durante a Instalação.
  
### <a name="machine-account"></a>Conta do computador

Assim como qualquer dispositivo Windows, o Nome do Computador pode ser renomeado clicando com o botão direito do mouse **no** Configurações \> **sobre** \> **renomear pc**.
  
Se você quiser renomear o computador depois de insinuá-lo em um domínio, use **Renomear-Computador**, um comando do PowerShell, seguido pelo novo nome do computador.
  
## <a name="related-topics"></a>Tópicos relacionados

[Planejar Salas do Microsoft Teams](rooms-plan.md)

[Requisitos das Salas do Microsoft Teams](requirements.md)
  
[Implantar Salas do Microsoft Teams](rooms-deploy.md)
  
[Configurar um console de Salas do Microsoft Teams](console.md)
  
[Gerenciar Salas do Microsoft Teams](rooms-manage.md)

[Pré-requisitos para educação Microsoft Store para Empresas e educação](/microsoft-store/prerequisites-microsoft-store-for-business)