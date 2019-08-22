---
title: Preparar seu ambiente
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection: M365-voice
description: Este artigo explica as preparações de infra-estrutura para a implantação de salas do Microsoft Teams.
ms.openlocfilehash: 5789f8138bf5ab9e12c77a8b2963ff32e7f33586
ms.sourcegitcommit: f2cdb2c1abc2c347d4dbdca659e026a08e60ac11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2019
ms.locfileid: "36493072"
---
# <a name="prepare-your-environment"></a>Preparar seu ambiente

Esta seção contém uma visão geral das etapas necessárias para preparar seu ambiente para que você possa usar todos os recursos dos salas do Microsoft Teams.
  
1. Prepare uma conta de dispositivo para cada console de salas do Microsoft Teams. Consulte [implantar salas do Microsoft Teams](room-systems-v2.md) para obter detalhes.
    
2. Verifique se existe uma conexão de rede/Internet para o dispositivo usar.  
    
   - Ele deve ser capaz de receber um endereço IP usando DHCP. (As salas do Microsoft Teams não podem ser configuradas com um endereço IP estático na primeira unidade de inicialização, mas posteriormente o IP estático para o dispositivo pode ser configurado no dispositivo ou na opção de upstream ou no roteador.)
    
   - Ele deve ter essas portas abertas (além de abrir as portas normais para mídia):
    
   - HTTPS: 443
    
   - HTTP: 80
    
   - Se sua rede é executada através de um proxy, você também precisa do endereço de proxy ou de informações do script.
    
     > [!NOTE]
     > O SkypeRoomSystemv2 não oferece suporte à entrada HDCP, pois foi observado que ela causa conflitos com a funcionalidade de ingestão HDMI (vídeo e áudio). Certifique-se que as chaves conectadas às Salas do Microsoft Teams estejam com as opções HDCP desativadas. 
  
3. Para aprimorar sua experiência, a Microsoft coleta dados. Para coletar dados, estes sites devem ser autorizados:
    
   - Ponto de extremidade do cliente de telemetria:https://vortex.data.microsoft.com/
    
   - Ponto de extremidade das configurações de telemetria:https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>Criar e testar uma conta de dispositivo

Uma *conta de dispositivo* é uma conta que o cliente de salas do Microsoft Teams usa para acessar recursos do Exchange, como calendário e para habilitar o Skype for Business. Consulte [implantar salas do Microsoft Teams](room-systems-v2.md) para obter detalhes.
  
### <a name="check-network-availability"></a>Verificar a disponibilidade da rede

Para funcionar corretamente, o dispositivo de salas Microsoft Teams deve ter acesso a uma rede com fio que atenda a esses requisitos:
  
- Acessar a instância do Active Directory ou do Azure Active Directory (Azure AD), bem como o servidores Microsoft Exchange e Skype for Business.
- Acesso a um servidor que pode fornecer um endereço IP usando DHCP. As salas do Microsoft Teams não podem ser configuradas com um endereço IP estático.
- Acessar as portas HTTP 80 e 443.
- Portas TCP e UDP configuradas conforme descrito em [requisitos de protocolo e porta para servidores](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) para implementações do Skype for Business Server no local ou [URLs e intervalos de endereços IP do Office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) para Microsoft Teams ou Skype for Business Online das.

> [!IMPORTANT]
> Use uma conexão de rede de 1 Gbps com fio para assegurar a largura de banda necessária. 

> [!NOTE]
> As atualizações de software para salas do Microsoft Teams são automaticamente baixadas da Microsoft Store para empresas. Veja [pré-requisitos para a Microsoft Store para empresas e instituições de ensino](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) para verificar se o console da sala poderá acessar a loja e a atualização automática.
  
### <a name="certificates"></a>Certificados

Seu dispositivo de salas do Microsoft Teams usa certificados para serviços Web do Exchange, Microsoft Teams ou Skype for Business, uso de rede e autenticação. Se os servidores relacionados usarem certificados públicos, o que ocorre com as implantações online e com algumas implantações locais, o administrador não precisará realizar nenhuma ação adicional para instalar os certificados. Por outro lado, se a autoridade de certificação for uma AC privada (típica em implantações locais), o dispositivo deverá confiar na AC, o que significa ter a AC e a cadeia de certificados de AC instaladas no dispositivo. Com a adição do dispositivo ao domínio, será possível executar essa tarefa automaticamente.
  
Você instalará os certificados da mesma forma como faria para qualquer outro cliente Windows.  
  
> [!NOTE]
> Os certificados podem ser necessários para que as salas do Microsoft Teams usem o Skype for Business Server.
  
### <a name="proxy"></a>Proxy

As salas do Microsoft Teams foram projetadas para herdar as configurações de proxy do sistema operacional Windows. Acesse o sistema operacional Windows da seguinte maneira:
  
1. Na interface do usuário de salas do Microsoft Teams, clique no ícone de engrenagem configurações em que você será solicitado a usar a senha de administrador local no dispositivo (a senha padrão é **SFB**).
2. Toque em **configurações** e, em seguida, toque no botão **ir para o Windows** e, em seguida, toque no botão **ir para administrador entrar** e, em seguida, clique no botão **administrador** (se o computador for associado ao domínio **, escolha outro usuário** e, em seguida, use .\Admin como o nome de usuário).
3. Na caixa de **pesquisa do Windows** na parte inferior esquerda, digite em regedit (ou seja, pressione a tela ou clique com o botão direito do mouse e escolha **Executar como administrador**).
4. Clique na pasta HKEY_USERS (você verá uma lista de SIDs de usuários do computador) e verifique se a pasta raiz HKEY_USERS está selecionada.
       
5. Clique em arquivo e, em seguida, escolha **Carregar Hive.**
6. Navegue até a pasta **C:\Users\Skype** e digite na caixa nome do arquivo NTuser. dat e pressione o botão abrir.

7. Você será solicitado a fornecer um nome de chave para seu Hive recém-carregado; Digite o Skype (agora você deve ver as configurações do registro para o usuário do Skype).
 
8. Abra a tecla Skype e navegue até as configurações do HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet e verifique se essas configurações foram inseridas: 
    
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    
    "MigrateProxy"=dword:00000001
    
    "ProxyEnable"=dword:00000001
    
    "ProxyServer"="xx.xx.xx.xx:8080"
    
    Se ProxyServer não existir, talvez seja necessário adicionar essa chave como uma cadeia de caracteres. Altere xx.xx.xx.xx:8080 para o ip/host e a porta de seu servidor proxy.
    
9. Quando terminar de fazer as alterações, realce a chave de usuário do Skype (pasta raiz do Skype) e escolha Descarregar Hive no menu arquivo do registro (você será solicitado a confirmar-selecione **Sim** ).
    
10. Agora, você pode fechar o editor do Registro e digitar logoff na caixa de pesquisa do Windows.
    
11. Voltando à tela de entrada, escolha o usuário **Skype**. Se todas as etapas anteriores tiverem sido bem-sucedidas, o dispositivo de salas do Microsoft Teams entrará com êxito.
    
Para usar esse aplicativo, você deve poder conectar-se aos pontos de extremidades descritos abaixo. Para ver os endereços IP, expanda a seção de endereços IP abaixo da tabela que descreve o fluxo de tráfego.
  
**Exemplos de Porta/Nome de host de proxy firewall**

|Objetivo|Origem ou credenciais|Porta de origem|Destino|CDN|ExpressRoute para Office 365|IP de destino|Porta de Destino|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Autenticação ou identidade  <br/> |Consulte [autenticação e identidade do Office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity) <br/> |||
|Portal e compartilhamento  <br/> |Consulte [portal e compartilhamento do Office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity) <br/> |||
|Sinalização SIP  <br/> |Computador cliente ou usuário conectado  <br/> |Portas efêmeras  <br/> |\*. contoso.com  <br/> |Não  <br/> |Sim  <br/> |[Intervalos de IP do Skype for Business](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Conferência Web com conexões PSOM (Modelo de Objeto Compartilhado Persistente)  <br/> |Computador cliente ou usuário conectado  <br/> |Portas efêmeras  <br/> |\*. contoso.com  <br/> |Não  <br/> |Sim  <br/> |[Intervalos de IP do Skype for Business](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Downloads HTTPS  <br/> |Computador cliente ou usuário conectado  <br/> |Portas efêmeras  <br/> |\*. contoso.com  <br/> |Não  <br/> |Sim  <br/> |[Intervalos de IP do Skype for Business](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Áudio  <br/> |Computador cliente ou usuário conectado  <br/> |TCP/UDP 50.000-50019  <br/> |\*. contoso.com  <br/> |Não  <br/> |Sim  <br/> |[Intervalos de IP do Skype for Business](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50.000-59.999  <br/> |
|Vídeo  <br/> |Computador cliente ou usuário conectado  <br/> |TCP/UDP 50.020-50039  <br/> |\*. contoso.com  <br/> |Não  <br/> |Sim  <br/> |[Intervalos de IP do Skype for Business](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50.000-59.999  <br/> |
|Compartilhamento de área de trabalho  <br/> |Computador cliente ou usuário conectado  <br/> |TCP/UDP 50.040-50059  <br/> |\*. contoso.com  <br/> |Não  <br/> |Sim  <br/> |[Intervalos de IP do Skype for Business](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, 50.000-59.999  <br/> |
|Notificações por push do Lync Mobile para o Lync Mobile 2010 em dispositivos iOS. Você não precisa disso para dispositivos móveis Android, Nokia Symbian ou Windows Phone.  <br/> |Computador cliente ou usuário conectado  <br/> |Portas efêmeras  <br/> |\*. contoso.com  <br/> |Não  <br/> |Sim  <br/> |[Intervalos de IP do Skype for Business](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 5223  <br/> |
|Telemetria do Skype  <br/> |Computador cliente ou usuário conectado  <br/> |Portas efêmeras  <br/> |skypemaprdsitus.trafficmanager.net  <br/> pipe.skype.com  <br/> |Não  <br/> |Não  <br/> |N/D  <br/> |TCP 443  <br/> |
|Dicas rápidas do cliente Skype  <br/> |Computador cliente ou usuário conectado  <br/> |Portas efêmeras  <br/> |quicktips.skypeforbusiness.com  <br/> |Não  <br/> |Não  <br/> |N/D  <br/> |TCP 443  <br/> |
   
> [!NOTE]
> O curinga para contoso.com e broadcast.skype.com representa uma longa lista de nós que são usados exclusivamente para o Office 365. 
  
### <a name="create-provisioning-packages"></a>Criar pacotes de provisionamento

Você usará pacotes de provisionamento para autenticar o Exchange Server ou o Office 365.
  
### <a name="admin-group-management"></a>Gerenciamento de grupo de administradores

Após o ingresso no domínio, você pode usar a Política de Grupo ou o Gerenciamento de Computador Local para definir um Grupo de Segurança como administrador local, da mesma forma como faria com um computador Windows em seu domínio. Qualquer membro desse grupo de segurança pode inserir as respectivas credenciais e desbloquear as configurações.
  
> [!NOTE]
> Se seu dispositivo de Salas do Microsoft Teams perder confiabilidade com o domínio (por exemplo, se você remover as Salas do Microsoft Teams do domínio após terem sido agregadas a ele), você não poderá autenticar esse dispositivo e abrir Configurações. A solução é fazer logon com a conta de Administrador local. 
  
## <a name="local-accounts"></a>Contas locais

### <a name="microsoft-teams-rooms-local-user-account"></a>Sala do Microsoft Teams conta de usuário local

A Conta de Dispositivo normalmente não usa senha. É possível atribuir a ela uma senha, mas há consequências, inclusive a possibilidade de o usuário ser bloqueado e não poder usar o aplicativo de console quando a senha expirar. Portanto, o administrador deve tomar cuidado para a senha não expirar.
  
### <a name="admin---local-administrator-account"></a>"Administrador" - Conta do Administrador Local

Sala de salas do Microsoft Teams a senha padrão é definida como "SFB". A senha pode ser alterada localmente acessando as configurações \> do Windows vá para Windows ou no arquivo Autounattend. XML (use o Gerenciador de imagem de sistema do Windows do ADK para fazer a alteração no arquivo XML).
  
> [!CAUTION]
> Certifique-se de alterar a senha das salas do Microsoft Teams assim que possível. 
  
A senha do Administrador Local também pode ser gerenciada por meio da configuração de uma política de grupo em que os administradores do domínio se tornam administradores locais.
  
A senha do Administrador local não é incluída como opção durante a Instalação.
  
### <a name="machine-account"></a>Conta do computador

Assim como qualquer dispositivo com Windows, o nome do computador pode ser renomeado clicando com o \> botão \> direito do mouse em configurações sobre renomear computador.
  
 Se você quiser renomear o computador após ingressar em um domínio, use o comando rename-Computer PowerShell seguido pelo novo nome do computador.
  
## <a name="see-also"></a>Confira também

[Planejar salas do Microsoft Teams](skype-room-systems-v2-0.md)

[Requisitos de salas do Microsoft Teams](requirements.md)
  
[Implantar salas do Microsoft Teams](room-systems-v2.md)
  
[Configurar um console de salas do Microsoft Teams](console.md)
  
[Gerenciar Salas do Microsoft Teams](skype-room-systems-v2.md)

[Pré-requisitos para a Microsoft Store para empresas e instituições de ensino](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) 
