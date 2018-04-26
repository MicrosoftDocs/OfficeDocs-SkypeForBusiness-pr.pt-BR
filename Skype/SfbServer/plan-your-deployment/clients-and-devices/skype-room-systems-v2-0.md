---
title: Planejar o Skype Room Systems versão 2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
description: Este artigo explica as considerações de planejamento relevantes para implantar sistemas de sala Skype v2, a próxima geração de sistemas de sala Skype.
ms.openlocfilehash: 372c920eaeaaee050e420cd25195565555426561
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
---
# <a name="plan-for-skype-room-systems-v2"></a>Planejar o Skype Room Systems versão 2
 
Este artigo explica as considerações de planejamento relevantes para implantar sistemas de sala Skype v2, a próxima geração de sistemas de sala Skype. 
  
 Sistemas de sala Skype v2 é a solução de conferência mais recente da Microsoft projetada para transformar a sala de reunião em um Skype rica e colaboração para a experiência de negócios. Os usuários apreciarão a interface familiar do Skype for Business, e os administradores de TI ficarão satisfeitos com a implantação e o gerenciamento fáceis do aplicativo Reunião do Skype para Windows 10. Sistemas de sala Skype v2 foi projetado para aproveitar o equipamento existente como painéis LCD para facilitar da instalação para trazer Skype for Business para sala de reunião.
  
Sistemas de sala Skype v2 usa um aplicativo UWP desenvolvido especificamente, que atua como a interface do usuário de reunião do Skype. Ele é executado em um 4 de Surface Pro ou Surface Pro em um modo de console (uma vez implantado o aplicativo UWP é o único aplicativo que serão executados no dispositivo) e ele requer sua própria conta de dispositivo em sua Skype para a implementação de negócios. Ele usa equipamentos existentes, como painéis de LCD e câmeras e microfones periféricos de custo relativamente baixo, para oferecer uma experiência de sala de reunião de qualidade. O software é atualizado via Windows Store e Windows Update.
  
Antes de preparar o ambiente, certifique-se de ter o hardware e o software necessários. Para obter mais informações, consulte [requisitos de v2 de sistemas de sala Skype](requirements.md). 
  
> [!NOTE]
> Sistemas de sala Skype v2 destina para uso com Skype para Business Server 2015 ou Skype Business Online. Plataformas anteriores, como o Lync Server 2013 não devem trabalhar com sistemas de sala Skype v2. 
  
Sistemas de sala Skype v2 é a solução de conferência mais recente da Microsoft projetada para transformar a sala de reunião em um Skype rica e colaboração para a experiência de negócios. Os usuários apreciarão a interface familiar do Skype for Business, e os administradores de TI ficarão satisfeitos com a implantação e o gerenciamento fáceis do aplicativo Reunião do Skype para Windows 10. Sistemas de sala Skype v2 foi projetado para aproveitar o equipamento existente como painéis LCD para facilitar da instalação para trazer Skype for Business para sala de reunião.
  
 **Projetado para o Skype for Business**
  
- Reuniões do Skype com apenas um toque
    
- Experiência de Reunião do Skype otimizada para salas com vídeo HD de preenchimento de tela e áudio de banda larga HD
    
- Todos os participantes podem se conectar à Reunião do Skype usando o dispositivo que quiserem, onde quer que estejam
    
- Convide pessoas a partir de seu diretório, onde você pode ver imediatamente a disponibilidade de cada contato, ou por chamada telefônica
    
- Compatível com os recursos de Conferência e Chamada PSTN do Skype for Business para substituir o telefone de conferência em sua sala
    
 **Transforme qualquer sala de reunião**
  
- Aplicativo dedicado à Reunião do Skype, otimizado para o controlador de tela touch de centro da mesa e para a grande tela frontal da sala
    
- Aproveite os investimentos existentes em seus projetores ou na tela frontal da sala
    
- Funciona para todos os tipos de espaços de reunião, de espaços pequenos a grandes salas de conferência
    
- Os dispositivos de áudio e vídeo certificados do Skype for Business estão disponíveis para vários tamanhos de sala
    
- Ingestão interna com fio para projetar o compartilhamento de área de trabalho para a sala e para a Reunião do Skype
    
- Seleção de usuário no aplicativo de reunião sala de áudio e vídeo dispositivos USB & #x 2776;
    
- Suporte de tela dual (para correspondência de sistema herdado) & #x 2777;
    
- Themability (temas internos e a capacidade de definir o tema personalizado) & #x 2777;
    
 **Fácil de implantar, simples de gerenciar**
  
- Dispositivo sempre ativo que aciona as telas automaticamente quando detecta pessoas na sala
    
- Implantação e atualização simples do aplicativo de Reunião do Skype da UWP (Plataforma Universal do Windows)
    
- O Windows AppLocker bloqueia o dispositivo para o aplicativo de Reunião do Skype
    
- Monitorado e gerenciado como um dispositivo do Windows 10 Enterprise via Intune e SCCM (MDM)
    
- Confiabilidade de nível empresarial
    
- Esforço mínimo para usuários finais devido à semelhança com a interface do usuário do Skype
    
- É executado no tablet Surface Pro 4
    
- Integrado status da sala console relatórios para clientes usando o pacote de gerenciamento do Microsoft Operations (consulte [management v2 de sistemas de sala Skype planejar com OMS](oms-management.md)) & #x 2776;
    
- Capacidade de fazer comentários para compilações públicas & #x 2777;
    
- Telemetria aprimorada em torno da reunião ingressar confiabilidade & #x 2777;
    
- Relatórios de OMS & #x 2777; adicionais
    
- Capacidade para o administrador de TI para configurar dispositivos remotamente & #x 2777;
    <!--  - Front-of-Room UX shows room details pre-meeting U2  -->
- É executado em um tablet Surface Pro & #x 2778;
    
- Suporta Windows 10 Enterprise criador de atualização (idioma inglês, compilação 1703) e #x 2778;
    
- Suporte para [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system) encaixa hardware & #x 2778;
    
- Suporte de OEM para controles do ambiente (Crestron) & #x 2778;
    
- Suporte para a [Série de MSR Polycom](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl) encaixa hardware & #x 2779;
    
- Suporte para [Logitech Brio](https://www.logitech.com/en-us/product/brio) & #x 2779;

- Suporte para [Lenovo Hub 500](https://www3.lenovo.com/us/en/hub500) encaixa hardware & #x277A;  
    
& #x 2776; -Recurso introduzido na atualização 1 (SW Ver. 2.0.2.0).
  
& #x 2777; -Recurso introduzido na atualização 2 (SW Ver. 3.0.6.0). 
  
& #x 2778; -Recurso introduzido na atualização 3 (SW Ver. 3.0.12.0). 
  
& #x 2779; -Recurso introduzido na atualização 4 (SW Ver. 3.0.15.0). 

& #x277A; -Recurso introduzido na atualização 5 (SW Ver. 3.1.98.0). 
  
## <a name="preparing-your-skype-for-business-environment"></a>Preparando o ambiente do Skype for Business

Esta seção contém uma visão geral das etapas necessárias para preparar o ambiente para que você possa usar todos os recursos de sistemas de sala Skype v2.
  
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
    
- Portas TCP e UDP configuradas conforme descrito em [requisitos de porta para o Lync Server 2013](https://technet.microsoft.com/en-us/library/gg398798%28v=ocs.15%29.aspx) for no local Skype para implementações de negócios, ou [URLs do Office 365 e intervalos de endereços IP](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) para Skype para implementações de negócios on-line.
    
> [!IMPORTANT]
> Use uma conexão de rede de 1 Gbps com fio para assegurar a largura de banda necessária.  
  
### <a name="certificates"></a>Certificados

Seu dispositivo v2 de sistemas de sala Skype usa certificados para serviços Web do Exchange, Skype de negócios, uso da rede e autenticação. Se os servidores relacionados usarem certificados públicos, o que ocorre com as implantações online e com algumas implantações locais, o administrador não precisará realizar nenhuma ação adicional para instalar os certificados. Por outro lado, se a autoridade de certificação for uma AC privada (típica em implantações locais), o dispositivo deverá confiar na AC, o que significa ter a AC e a cadeia de certificados de AC instaladas no dispositivo. Com a adição do dispositivo ao domínio, será possível executar essa tarefa automaticamente.
  
Você instalará os certificados da mesma forma como faria para qualquer outro cliente Windows.  
  
> [!NOTE]
> Certificados podem ser necessárias para que o Skype sala sistemas v2 usar Skype para servidor de negócios. 
  
### <a name="proxy"></a>Proxy

Sistemas de sala Skype v2 foi projetado para herdar as configurações de Proxy do sistema operacional Windows. Acesse o sistema operacional Windows da seguinte maneira:
  
1. Na interface do usuário a sistemas de sala Skype v2, clique no ícone de engrenagem configurações onde será solicitado a senha de administrador local no dispositivo (a senha padrão é "sfb").
    
2. Toque em "Configurações" seguidas tocando no botão "Ir para o Windows" e no "receber Admin entrar no" botão e clicando no botão "Administrador" (se o computador está unido ao domínio escolha "Outro usuário", use. \admin como o nome de usuário).
    
3. Na "pesquisa Windows" caixa tipo de inferior esquerdo Regedit (seja longo press tela ou direita clique e escolha "Executar como administrador").
    
4. Clique na pasta HKEY_USERS (você verá uma lista de SIDs de usuários do computador) e verifique se a pasta raiz HKEY_USERS está selecionada.
    
    Você será solicitado para um nome de chave para seu Hive carregado recentemente; Digite Skype (agora você deve ver as configurações do registro para o usuário Skype).
    
5. Clique em Arquivo e escolha "Carregar Hive".
    
6. Navegue até a pasta "C:\Usuários\Skype", digite NTUSER.dat na caixa Nome do arquivo e pressione o botão Abrir.
    
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

[Requisitos de v2 de sistemas de sala do Skype](requirements.md)
  
[Implantar Skype sala v2 de sistemas](../../deploy/deploy-clients/room-systems-v2.md)
  
[Configurar um console v2 de sistemas de sala do Skype](../../deploy/deploy-clients/console.md)
  
[Gerenciar Skype sala v2 de sistemas](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

