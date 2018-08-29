---
title: Implantar o Portal de Web administrativo do SRS v1 no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
description: O Skype para sistemas de sala Business Server Skype v1 (SRS v1, anteriormente conhecido como o sistema de sala do Lync) administrativas Portal da Web é um portal da web que as organizações podem usar para manter suas salas de conferência de sistemas de sala Skype. Os administradores podem usar o Portal da Web SRS v1 administrativas para monitorar a integridade do dispositivo, por exemplo por meio do monitoramento de dispositivos de áudio/vídeo. Com esse portal, os administradores podem coletar remotamente informações de diagnóstico para monitorar a integridade da sala de conferência.
ms.openlocfilehash: 6aa7b0d4f36fbffe29a27f77209fb6f2cf312c05
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23248128"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a>Implantar o Portal de Web administrativo do SRS v1 no Skype para Business Server

O Skype para sistemas de sala Business Server Skype v1 (SRS v1, anteriormente conhecido como o sistema de sala do Lync) administrativas Portal da Web é um portal da web que as organizações podem usar para manter suas salas de conferência de sistemas de sala Skype. Os administradores podem usar o Portal da Web SRS v1 administrativas para monitorar a integridade do dispositivo, por exemplo por meio do monitoramento de dispositivos de áudio/vídeo. Com esse portal, os administradores podem coletar remotamente informações de diagnóstico para monitorar a integridade da sala de conferência.

Para usar esse recurso, o Portal da Web administrativo SRS v1 precisa ser implantado em cada Skype para Business Server servidor Front-End. Este guia fornece instruções para os administradores sobre como instalar e configurar o Portal da Web Administrativo do SRS. Ele foi projetado para administradores que tem conhecimento do Skype para administração de servidor de negócios, e que tenha direitos de usuário de administrador para modificar o Skype para a topologia de servidor de negócios.

Após o v1 SRS que administrativas Portal da Web é implantado no servidor, os administradores podem verificar os dispositivos do status SRS v1 por logon ao site de seus próprios computadores ou laptops.

> [!IMPORTANT]
> Baixe o [Microsoft Skype sala v1 de sistemas e Portal da Web administrativo para Skype para Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).

Neste tópico:

- [Configurar seu ambiente para o Portal da Web Administrativo do SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)

- [Instalar o Portal da Web Administrativo do SRS v1](room-system-v1-administrative-web-portal.md#Install_SRS)

- [Usar o Portal da Web Administrativo do SRS](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a>Configurar seu ambiente para o Portal da Web Administrativo do SRS v1
<a name="Config_Env"> </a>

Para usar o Portal da Web Administrativo do SRS v1, será necessário instalar ou configurar os pré-requisitos a seguir.

> [!IMPORTANT]
> Se o servidor estiver configurado com a autenticação Kerberos e NTLM e o SRS estiver em execução em um computador que não tenha ingressado no domínio, haverá falha na autenticação Kerberos e o usuário não verá o status do SRS no portal administrativo. Para resolver esse problema, configure o servidor com autenticação NTLM ou com autenticação NTLM e TLS-DSK (sem Kerberos), ou ingresse o computador com SRS no domínio.

1. Instale o Skype para atualizações cumulativas do Business Server no Skype para a topologia de servidor de negócios.

    Para obter a atualização ou consulte o que está incluído com ele, consulte [atualizações para Skype para Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).

2. Crie um usuário do Active Directory habilitado para SIP.

    O Portal da Web administrativo SRS v1 usa essas credenciais para consultar informações do Skype para Business Server. O nome de usuário nos exemplos fornecidos é LRSApp.

3. Crie um grupo de segurança do Active Directory com o nome LRSSupportAdminGroup.

    Crie o grupo com Escopo do Grupo como Global e Tipo de Grupo como Segurança. Os usuários habilitados para SIP que forem adicionados a este grupo serão autorizados a ver a lista de salas e a executar determinados comandos, como coletar logs.

4. Crie um grupo de segurança do Active Directory com o nome LRSFullAccessAdminGroup. 

    Crie o grupo com Escopo do Grupo como Global e Tipo de Grupo como Segurança. Os usuários habilitados para SIP que forem adicionados a esse grupo serão autorizados a usar toda a funcionalidade do portal de administração em uma única sala do Skype. Para incluir suporte para o gerenciamento em massa de salas do Skype, consulte a etapa 5. 

     ![Lista de grupos administrativos com a função de grupo de segurança](../../media/LRS_LRSFullAccessAdminGroup.png)

5. Crie um grupo de segurança do Active Directory com o nome LRSPowerUserAdminsGroup.

    Crie o grupo com Escopo do Grupo como Global e Tipo de Grupo como Segurança. Os usuários habilitados para SIP adicionados a este grupo estão autorizados a usar todas as funcionalidades de portal de administração incluindo gerenciamento de massa do Skype para salas de negócios.

6. Adicione LRSFullAccessAdminGroup como membro do LRSSupportAdminGroup.

     ![Página Membros de Propriedades LRSSupportAdminGroup](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. Crie um usuário do Active Directory habilitado para SIP com o nome LRSSupport. Adicione-o a LRSSupportAdminGroup.

     ![Página Membros de Propriedades LRSSupportAdminGroup](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. Instale o [ASP.NET MVC 4 para o Visual Studio 2010 SP1 e Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).

## <a name="install-the-srs-v1-administrative-web-portal"></a>Instalar o Portal da Web Administrativo do SRS v1
<a name="Install_SRS"> </a>

Baixe o [Microsoft Skype sala v1 de sistemas e Portal da Web administrativo para Skype para Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).

Para instalar o Portal da Web Administrativo do SRS v1, use as etapas a seguir.

1. Configure a porta de aplicativos confiáveis executando o seguinte cmdlet no Skype do Shell de gerenciamento do servidor de negócios:

   ```
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. Para instalar o Portal da Sala de Reunião, baixe o arquivo **MeetingRoomPortalInstaller.msi** e execute-o como administrador.

3. Abra o arquivo Web.config no seguinte local:

    %Arquivos de Programas%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler\

4. No arquivo Web. config, altere o PortalUserName para o nome de usuário criado na etapa 2, sob a seção "[configurar seu ambiente para o Portal da Web administrativo SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)" (o nome recomendado na etapa é LRSApp):

    ```
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. Como o Portal de Administração do SRS v1 é um aplicativo confiável, você não precisa fornecer a senha na configuração do portal. Se o usuário estiver usando um registrador diferente do registrador local, você precisará especificar o registrador para ele adicionando a seguinte linha no arquivo Web.Config: 

   ```
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. Se a porta usada for diferente de 5061, adicione a seguinte linha no arquivo Web.Config: 

   ```
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a>Verificar a instalação do Portal da Web Administrativo do SRS

Para verificar a instalação do Portal da Web Administrativo do SRS v1, faça o seguinte:

1. Em um servidor front-end, vá para a seguinte URL:

    https://\<servidor fe\>/lrs

    Você não deverá ver nenhum erro, como mostrado na imagem a seguir:

     ![Tela de entrada no portal admin do sistema Lync Room](../../media/LRS_AdminPortalSignIn.png)

2. Se não vir nenhum erro, tente acessar a seguinte URL a partir de qualquer outro computador na topologia:

    https://\<servidor fe\>/lrs

    Para acessar a página, você precisará adicionar os registros DNS conforme descrito em "[necessário registros DNS para o cliente na entrada automática](https://go.microsoft.com/fwlink/p/?LinkId=318056)."

## <a name="use-the-srs-administrative-web-portal"></a>Usar o Portal da Web Administrativo do SRS
<a name="Use_Portal"> </a>

Após implantar o SRS no servidor, você poderá verificar o status de todas as salas do SRS entrando no Portal da Web Administrativo do SRS v1 em um navegador.

### <a name="sign-in"></a>Entrar

1. Navegue até a seguinte URL:

    https://\<servidor fe\>/lrs

2. Insira as credenciais da conta LRSSupport ou de uma conta que tenha sido adicionada ao grupo de segurança LRSSupportAdminGroup.

![Tela de entrada no portal admin do sistema Lync Room](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a>Página de resumo do Portal da Web Administrativo do SRS

A página de resumo fornece as seguintes informações sobre todas as salas do SRS implantadas no servidor:

- **Marca** O nome personalizado que o administrador concede à sala. A Marca pode ser definida no portal quando você clica no nome da sala.

- **Integridade** O status de integridade da sala, que é derivado do status de integridade agregado da sala, que é mostrado na seção de integridade da página Configurações de sala.

- **Próxima reunião** A data e hora que a próxima reunião foi agendada.

- **Modelo de versão, fabricante, SRS** Esses valores são predefinidos no SRS. Dependendo do fabricante, esses campos podem ser deixados em branco.

- **Última atualização** Exibe a última vez em que a página da web foi atualizada.

![Visualização de Resumo do Portal de Administração do Sistema de Salas do Lync](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> Você verá o menu de gerenciamento em massa apenas se você fizer parte do grupo de segurança LRSPowerUserAdminsGroup.

### <a name="srs-room-information"></a>Informações da Sala do SRS

A seção Informações da Sala do portal permite que você veja e configure salas do SRS individuais. Ela contém quatro seções: Configurações, Detalhes, Registro em Log e Integridade.

#### <a name="settings"></a>Configurações

Na seção Configurações, você pode definir a senha, a marca da sala e os níveis de volume padrão da sala. Se você definir essas configurações, as alterações serão replicadas somente depois que o console do SRS for reiniciado. Você só verá as configurações de Atualizações do Sistema para dispositivos do SRS que estiverem usando a versão 15.12 e posteriores.

![Configurações de Salas do Portal de Administração do Sistema de Salas do Lync](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a>Detalhes

Seção detalhes do fornece um resumo de somente leitura das configurações da sala SRS, incluindo: a hora da última atualização; próxima reunião; últimas atualizações, manutenção e calibragem; configurações de campainha; microfone e alto-falante do padrão versão; URI DO SIP; número de telas e detalhes sobre cada tela; status e a atividade.

![Visualização de Detalhes do Portal de Administração do Sistema de Salas](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a>Solução de Problemas

A seção Solução de Problemas pode ser usada para coletar logs remotamente e salvá-los em um local especificado. Você também pode reiniciar o console do SRS (interface do usuário do SRS) ou reiniciar o sistema inteiro. Para coletar logs, forneça um caminho de pasta no formato especificado e verifique se a pasta tem permissões de gravação concedidas à conta do computador do SRS. Se o tamanho do log for muito grande, a coleta de logs poderá levar até cinco minutos para ser concluída. Atualize a página para ver o status mais recente.

#### <a name="health"></a>Integridade

A seção de integridade, fornece uma indicação visual da integridade do Skype para conexão Business Server, dispositivo de áudio, dispositivo de vídeo, o estado de resiliência e dispositivo de tela.

![Integridade de Salas do Portal de Administração do Sistema de Salas do Lync](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a>Observações adicionais sobre o Portal da Web Administrativo

> [!NOTE]
>  Alterações de configuração são aplicadas somente depois que o sistema SRS for reiniciado. > se a senha da conta LRSApp expirar, você não poderá ver o status das salas. Configurar a senha da conta LRSAppuser para que ele nunca expira ou não se esqueça de atualizar a senha, quando ele está perto expiração. > portal da web administrativo de SRS o é suportado para implantações de locais somente.

### <a name="bulk-management"></a>Gerenciamento em massa 

O gerenciamento em massa das salas do SRS é um recurso criado para administradores de TI avançados, com o objetivo de simplificar seu fluxo de trabalho e oferecer uma ferramenta conveniente com economia de tempo para gerenciar remotamente várias salas de uma vez.

Para ver essa funcionalidade, o usuário precisa ser provisionado como um membro do grupo de segurança especial, **LRSPowerUserAdminsGroup**.  

Não há limite para o número de salas do SRS que podem ser selecionadas para gerenciamento em massa. No entanto, você pode realizar apenas uma operação de gerenciamento em massa por vez.

Para executar uma operação de gerenciamento em massa, selecione as salas que você deseja monitorar e clique no menu de gerenciamento em massa. 

### <a name="frequently-asked-questions"></a>Perguntas frequentes

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>Por que não posso entrar no portal da web administrativo?

Quando você abre https://localhost/lrs, será possível ver a página de entrada, mas quando você digitar suas credenciais, você não conseguir entrar. Nesse caso, você deve abrir https://FQDNofFEserver/SRS para entrar no portal da web administrativo.

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a>Por que não posso ver v1 SRS no portal do web administrativo?

- Verifique se você tem contas do SRS na sua implantação e se elas foram criadas de acordo com as recomendações de implantação do Portal da Web Administrativo do SRS. Verifique se que as contas SRS são provisionadas usando o Enable-CsMeetingRoom não Enable-CsUser, o Skype para Business Server.

- Se você tiver criado contas SRS e não pode ver as contas no portal da web administrativo, coletar logs do servidor usando o Skype para ferramenta de log do servidor de negócios com o componente de **MeetingPortal** selecionado e depois enviá-las ao seu contato do suporte SRS.

- Se você tiver criado contas do SRS e não conseguir ver as contas no Portal da Web Administrativo, colete os logs do cliente usando o Fiddler e também copie o log do console das ferramentas de desenvolvimento de navegador. Em seguida, envie-os para seu contato de suporte do SRS. Você também pode modificar o valor do nível de rastreamento no Web.config para obter um log mais detalhado.

  ```
  <system.diagnostics>
    <switches>
      <!--
      This switch controls logging message levels. 0 implies
      logging is turned off. 1 implies only errors are logged,
      2 implies errors &amp; warnings. 4 is the most detailed.
      -->
      <add name="TraceLevelSwitch" value="3" />
    </switches>
  </system.diagnostics>
  ```

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a>Por que não posso ver o status da SRS no portal do web administrativo?

- Verifique se a conta de usuário LRSApp está habilitada para SIP.

- Se você ainda estiver tendo problemas, coletar o arquivo **Trace** no sistema SRS de D:\Tracing\LRSAdminLogs\, e depois enviá-la ao seu contato do suporte SRS.

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a>Por que eu não podem ver os menus de gerenciamento em massa para SRS no portal do web administrativo?

Certifique-se de que a conta de usuário LRSApp é habilitado para SIP e faz parte do grupo de segurança LRSPowerUserAdminsGroup.

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-skype-room-systems-v2"></a>O Portal da Web Administrativo do SRS v1 funciona com o Skype Room Systems v2?

Não.


