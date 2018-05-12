---
title: Prepare seu ambiente
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
description: Este artigo explica as preparações de infraestrutura para implantar sistemas de sala Skype v2.
ms.openlocfilehash: b8f1e52686cfab957f2fb81a33deecc778514673
ms.sourcegitcommit: febd51fd7988602a8c9839e4e9872ae8f5d77c63
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2018
---
# <a name="prepare-your-environment"></a>Prepare seu ambiente

Esta seção contém uma visão geral das etapas necessárias para preparar seu Skype para o ambiente de negócios para que você possa usar todos os recursos de sistemas de sala Skype v2.
  
1. Prepare uma conta do dispositivo para cada console v2 de sistemas de sala Skype. Consulte [v2 implantar sistemas de sala Skype](../../deploy/deploy-clients/room-systems-v2.md) para obter detalhes.
    
2. Verifique se existe uma conexão de rede/Internet para o dispositivo usar.  
    
  - Ele deve ser capaz de receber um endereço IP usando DHCP (Observação: os sistemas de sala Skype v2 não pode ser configurado com um endereço IP estático na primeira inicialização unidade)
    
  - Ela deve ter portas abertas (além de abrir as portas normais para a mídia do Skype for Business):
    
  - HTTPS: 443
    
  - HTTP: 80
    
  - Se sua rede é executada através de um proxy, você também precisa do endereço de proxy ou de informações do script.
    
    > [!NOTE]
    > Sistemas de sala Skype v2 não oferece suporte a entrada HDCP, o que foi observada causa problemas com HDMI inclusão funcionalidade (vídeo, áudio). Tome cuidado para garantir que os switches conectados ao v2 de sistemas de sala Skype tenham opções HDCP desativadas. 
  
3. Para aprimorar sua experiência, a Microsoft coleta dados. Para coletar dados, estes sites devem ser autorizados:
    
  - Ponto de extremidade de cliente de telemetria:https://vortex.data.microsoft.com/
    
  - Ponto de extremidade de configurações de telemetria:https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>Criar e testar uma conta de dispositivo

Uma *conta de dispositivo* é uma conta que o cliente de v2 de sistemas de sala Skype usa para acessar os recursos do Exchange, como calendário e habilitar Skype para negócios. Consulte [v2 implantar sistemas de sala Skype](../../deploy/deploy-clients/room-systems-v2.md) para obter detalhes.
  
### <a name="check-network-availability"></a>Verificar a disponibilidade da rede

Para funcionar corretamente, o dispositivo de v2 Skype sistemas de sala deve ter acesso a uma rede com fio que atende aos seguintes requisitos:
  
- Acessar a instância do Active Directory ou do Azure Active Directory (Azure AD), bem como o servidores Microsoft Exchange e Skype for Business.
    
- Acesso a um servidor que pode fornecer um endereço IP usando DHCP. Sistemas de sala Skype v2 não pode ser configurado com um endereço IP estático.
    
- Acessar as portas HTTP 80 e 443.
    
- Portas TCP e UDP configuradas conforme descrito em [requisitos de porta e protocolo para servidores](../network-requirements/ports-and-protocols.md) for no local Skype para implementações de negócios, ou [URLs do Office 365 e intervalos de endereços IP](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) para Skype para implementações de negócios on-line.
    
> [!IMPORTANT]
> Use uma conexão de rede de 1 Gbps com fio para assegurar a largura de banda necessária.  
  
### <a name="certificates"></a>Certificados

Seu dispositivo v2 de sistemas de sala Skype usa certificados para serviços Web do Exchange, Skype de negócios, uso da rede e autenticação. Se os servidores relacionados usarem certificados públicos, o que ocorre com as implantações online e com algumas implantações locais, o administrador não precisará realizar nenhuma ação adicional para instalar os certificados. Por outro lado, se a autoridade de certificação for uma AC privada (típica em implantações locais), o dispositivo deverá confiar na AC, o que significa ter a AC e a cadeia de certificados de AC instaladas no dispositivo. Com a adição do dispositivo ao domínio, será possível executar essa tarefa automaticamente.
  
Você instalará os certificados da mesma forma como faria para qualquer outro cliente Windows.  
  
> [!NOTE]
> Certificados podem ser necessárias para que o Skype sala sistemas v2 usar Skype para servidor de negócios. 
  
### <a name="proxy"></a>Proxy

Sistemas de sala Skype v2 foi projetado para herdar as configurações de Proxy do sistema operacional Windows. Acesse o sistema operacional Windows da seguinte maneira:
  
1. Na interface do usuário a sistemas de sala Skype v2, clique no ícone de engrenagem configurações onde será solicitado a senha de administrador local no dispositivo (a senha padrão é **sfb**).
    
2. Toque em **configurações** seguido por um toque no botão **Ir para o Windows** e, em seguida, toque no botão **Ir para administração entrar** e clicando no botão de **administrador** (se o computador está unido ao domínio escolher **Outro usuário,** e então usar . \admin como o nome de usuário).
    
3. No **Windows de pesquisa** caixa tipo da esquerda inferior Regedit (tanto tempo pressione tela ou clique com botão direito e escolha **Executar como administrador**).
    
4. Clique na pasta HKEY_USERS (você verá uma lista de SIDs de usuários do computador) e verifique se a pasta raiz HKEY_USERS está selecionada.
    
    Você será solicitado para um nome de chave para seu Hive carregado recentemente; Digite Skype (agora você deve ver as configurações do registro para o usuário Skype).
    
5. Clique em arquivo e escolha **Carregar Hive.**
    
6. Procure a para o **C:\Users\Skype** pasta e digite o nome de arquivo. dat de caixa em pressione o botão Abrir
    
7. Abra a chave do Skype e navegue até HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet configurações e certifique-se de que essas configurações são inseridas: 
    
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    
    "MigrateProxy" = DWORD: 00000001
    
    "ProxyEnable" = DWORD: 00000001
    
    "ProxyServer"="xx.xx.xx.xx:8080"
    
    Se ProxyServer não existir, talvez seja necessário adicionar essa chave como uma cadeia de caracteres. Altere xx.xx.xx.xx:8080 para o ip/host e a porta de seu servidor proxy.
    
8. Depois que terminar de fazer as alterações, realce o usuário Skype principais (pasta raiz do Skype) e escolha descarregar seção no menu Arquivo do registro (será solicitado para confirmação - selecionar **Sim** ).
    
9. Agora, você pode fechar o editor do Registro e digitar logoff na caixa de pesquisa do Windows.
    
10. Voltando à tela de entrada, escolha o usuário **Skype**. Se todas as etapas anteriores forem bem-sucedidas, o dispositivo de v2 Skype sala sistemas serão entrar com êxito.
    
Para usar esse aplicativo, você deve poder conectar-se aos pontos de extremidades descritos abaixo. Para ver os endereços IP, expanda a seção de endereços IP abaixo da tabela que descreve o fluxo de tráfego.
  
**Exemplos de porta do nomes de Host de Proxy de firewall**

|**Finalidade**|**Origem ou credenciais**|**Porta de origem**|**Destino**|**CDN**|**ExpressRoute para o Office 365**|**Destino IP**|**Porta de destino**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Autenticação ou identidade  <br/> |Consulte a [identidade e autenticação do Office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity) <br/> |||
|Portal e compartilhamento  <br/> |Consulte o [portal e compartilhado do Office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity) <br/> |||
|Sinalização SIP  <br/> |Computador cliente ou usuário conectado  <br/> |Portas efêmeras  <br/> |\*. contoso.com  <br/> |Não  <br/> |Sim  <br/> |[Skype para intervalos de IP de negócios](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Conferência Web com conexões PSOM (Modelo de Objeto Compartilhado Persistente)  <br/> |Computador cliente ou usuário conectado  <br/> |Portas efêmeras  <br/> |\*. contoso.com  <br/> |Não  <br/> |Sim  <br/> |[Skype para intervalos de IP de negócios](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Downloads HTTPS  <br/> |Computador cliente ou usuário conectado  <br/> |Portas efêmeras  <br/> |\*. contoso.com  <br/> |Não  <br/> |Sim  <br/> |[Skype para intervalos de IP de negócios](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Áudio  <br/> |Computador cliente ou usuário conectado  <br/> |TCP/UDP 50.000-50019  <br/> |\*. contoso.com  <br/> |Não  <br/> |Sim  <br/> |[Skype para intervalos de IP de negócios](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50.000-59.999  <br/> |
|Vídeo  <br/> |Computador cliente ou usuário conectado  <br/> |TCP/UDP 50.020-50039  <br/> |\*. contoso.com  <br/> |Não  <br/> |Sim  <br/> |[Skype para intervalos de IP de negócios](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50.000-59.999  <br/> |
|Compartilhamento de área de trabalho  <br/> |Computador cliente ou usuário conectado  <br/> |TCP/UDP 50.040-50059  <br/> |\*. contoso.com  <br/> |Não  <br/> |Sim  <br/> |[Skype para intervalos de IP de negócios](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, 50.000-59.999  <br/> |
|Notificações por push do Lync Mobile para o Lync Mobile 2010 em dispositivos iOS. Você não precisa disso para dispositivos móveis Android, Nokia Symbian ou Windows Phone.  <br/> |Computador cliente ou usuário conectado  <br/> |Portas efêmeras  <br/> |\*. contoso.com  <br/> |Não  <br/> |Sim  <br/> |[Skype para intervalos de IP de negócios](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 5223  <br/> |
|Telemetria do Skype  <br/> |Computador cliente ou usuário conectado  <br/> |Portas efêmeras  <br/> |skypemaprdsitus.trafficmanager.NET  <br/> pipe.Skype.com  <br/> |Não  <br/> |Não  <br/> |N/D  <br/> |TCP 443  <br/> |
|Dicas rápidas do cliente Skype  <br/> |Computador cliente ou usuário conectado  <br/> |Portas efêmeras  <br/> |quicktips.skypeforbusiness.com  <br/> |Não  <br/> |Não  <br/> |N/D  <br/> |TCP 443  <br/> |
   
> [!NOTE]
> O curinga para contoso.com e broadcast.skype.com representa uma longa lista de nós que são usados exclusivamente para o Office 365. 
  
### <a name="create-provisioning-packages"></a>Criar pacotes de provisionamento

Você usará pacotes de provisionamento para fazer autenticação no Exchange Server ou no Skype for Business Server.
  
### <a name="admin-group-management"></a>Gerenciamento de grupo de administradores

Após o ingresso no domínio, você pode usar a Política de Grupo ou o Gerenciamento de Computador Local para definir um Grupo de Segurança como administrador local, da mesma forma como faria com um computador Windows em seu domínio. Qualquer membro desse grupo de segurança pode inserir as respectivas credenciais e desbloquear as configurações.
  
> [!NOTE]
> Se o seu dispositivo v2 de sistemas de sala Skype perde a confiança com o domínio (por exemplo, se você remover o v2 Skype sala sistemas do domínio depois que ele for unido ao domínio), você não conseguirá autenticar no dispositivo e abra o backup das configurações. Como alternativa, é possível entrar com a conta de Administrador local. 
  
## <a name="local-accounts"></a>Contas locais

### <a name="skype-room-systems-local-user-account"></a>Conta de usuário local do Skype Room Systems

A Conta de Dispositivo normalmente não usa senha. É possível atribuir a ela uma senha, mas há consequências, inclusive a possibilidade de o usuário ser bloqueado e não poder usar o aplicativo de console quando a senha expirar. Portanto, o administrador deve tomar cuidado para a senha não expirar.
  
### <a name="admin---local-administrator-account"></a>"Administrador" - Conta do Administrador Local

Senha do Skype sala sistemas v2 padrão é definida como "sfb". A senha pode ser alterada localmente, indo para configurações do Windows \> ir para Windows ou no arquivo Autounattend (use o Gerenciador de imagem de sistema do Windows do ADK para fazer a mudança para o arquivo xml).
  
> [!CAUTION]
> Certifique-se de alterar a senha de v2 de sistemas de sala Skype assim que possível. 
  
A senha do Administrador Local também pode ser gerenciada por meio da configuração de uma política de grupo em que os administradores do domínio se tornam administradores locais.
  
A senha do Administrador local não é incluída como opção durante a Instalação.
  
### <a name="machine-account"></a>Conta do computador

Muito como qualquer dispositivo do Windows, o nome da máquina podem ser renomeado com o botão direito do mouse nas configurações \> sobre \> PC renomear.
  
 Se você gostaria de renomear o computador após ingressá-lo a um domínio, use o comando PowerShell renomear computador seguido pelo nome do novo do computador.
  
## <a name="see-also"></a>Consulte também

#### 

[Planejar a sala Skype v2 de sistemas](skype-room-systems-v2-0.md)

[Requisitos de v2 de sistemas de sala do Skype](requirements.md)
  
[Implantar Skype sala v2 de sistemas](../../deploy/deploy-clients/room-systems-v2.md)
  
[Configurar um console v2 de sistemas de sala do Skype](../../deploy/deploy-clients/console.md)
  
[Gerenciar Skype sala v2 de sistemas](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

