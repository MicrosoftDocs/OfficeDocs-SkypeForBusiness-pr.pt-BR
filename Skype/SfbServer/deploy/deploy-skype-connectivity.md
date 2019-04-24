---
title: Implantar a conectividade do Skype no Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 'Resumo: Saiba como conectar Skype para Business Server com Skype consumidor. Também conhecida como a conectividade do Skype.'
ms.openlocfilehash: 3dd48661b230f4e780505be4aeb05bbe9ff82340
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219687"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Implantar a conectividade do Skype no Skype para Business Server
 
**Resumo:** Saiba como conectar Skype para Business Server com Skype consumidor. Também conhecida como a conectividade do Skype.
  
Este artigo apresenta o passo a passo da implantação da Conectividade Skype.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Visão geral da Conectividade Skype para profissionais de TI

Conectividade do Skype fornece Skype para usuários empresariais a capacidade de pesquisar e adicionar usuários do Skype. Conectividade do Skype é um recurso do Skype for Business que lhe permite habilitar a pesquisa de diretório e federação com usuários do Skype. Após habilitar a conectividade do Skype sua Skype para usuários comerciais poderão procurar e adicionar usuários do Skype.
  
## <a name="skype-directory-search"></a>Pesquisa de diretórios do Skype

A funcionalidade de pesquisa de diretórios do Skype permite que os usuários do Skype for Business pesquisem contatos do Skype. A funcionalidade de pesquisa permite que os usuários façam pesquisas usando as opções a seguir:
  
- **Pesquisa por nome para exibição, exemplo "Carlos Grilo"** - isso poderia retornar o número de resultados, para que você não pode encontrar o que você estiver procurando por.
    
- **Pesquisar por nome de exibição mais local, o exemplo "John Doe em Barcelona"** - isso reduzirá os resultados da pesquisa para baixo consideravelmente.
    
- **Pesquisa por email, exemplo "johndoe@outlook.com"** - isso deve retornar um resultado na maioria dos casos; aquele que corresponde exatamente o email especificado. Mas, se o mesmo email estiver associado a mais de uma conta, vários resultados podem ser retornados.
    
- **Pesquisar por número de telefone, exemplo "123-123-1234"** - isso deve retornar um resultado na maioria dos casos; aquele que corresponde exatamente o telefone especificado. Número de telefone deve incluir o código de país (por exemplo, 1-xxx-yyy-zzzz). Se o mesmo número de telefone estiver associado a mais de uma conta, vários resultados podem ser retornados.
    
- **Pesquisa por nome Skype, exemplo "JohnDoe1456"** - se for encontrada correspondência exata, ele será retornado como o primeiro resultado. Outras possíveis correspondências "name" podem ser retornadas.
    
    > [!NOTE]
    > A Pesquisa de Diretório do Skype deve ser capaz de se comunicar com os seguintes endereços IP na porta 443: 104.40.75.246, 23.101.135.34 e 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Matriz de implantação suportada para a pesquisa de diretórios do Skype

A tabela a seguir apresenta o suporte para a pesquisa de diretórios do Skype.
  

||**Skype para negócios servidor Front-End**|**Front-end do Lync Server 2013 (ou versões anteriores)**|**Comentários**|
|:-----|:-----|:-----|:-----|
|Skype para o servidor de borda de negócios  <br/> |Com suporte  <br/> |Sem suporte  <br/> |Skype para servidor de negócios e de borda são pré-requisitos para a pesquisa de diretório do Skype  <br/> |
|Skype para o servidor de borda Business + borda do Lync Server 2013 implantada lado a lado  <br/> |Com suporte  <br/> |Sem suporte  <br/> |O tráfego da pesquisa de diretórios do Skype passa pelos servidores de borda do Skype for Business. O tráfego de federação passa pela borda configura pelo administrador. Por exemplo, o administrador pode optar por continuar a enviar o tráfego da federação por meio dos servidores de borda do Lync Server 2013, que não dão suporte à pesquisa de diretórios do Skype.  <br/> |
|Servidor de borda do Lync Server 2013 (ou anterior)  <br/> |Sem suporte  <br/> |Sem suporte  <br/> ||
   
> [!NOTE]
> Serviço AddressBook executando Skype para negócios servidor Front-End localiza a borda pela existência da porta Skype pesquisa 4443 no servidor de borda. 
  
> [!NOTE]
> No caso de um cliente tiver vários sites em sua implantação no local e, se tiver implantado apenas um Skype para servidor de borda de negócios/pool de servidores, clique pesquisar o tráfego de todos os sites serão efetuadas o único servidor de borda disponível. O administrador deve certificar-se de que os pools de todos os sites podem acessar o Skype implantado para servidor de borda de negócios/pool de servidores. 
  
> [!NOTE]
> O serviço de gráficos do Skype limitará as solicitações de pesquisa de clientes locais ou do Office 365 se a taxa de solicitações exceder 15 solicitações/segundo. 
  
> [!NOTE]
> Nos clientes corporativos de grande porte com implantações locais, os domínios deverão ser autorizados no serviço de pesquisa do Skype para aumentar as taxas de solicitações. 
  
> [!NOTE]
> Skype para Business Server irá acelerar solicitações de entrada, se houver muitas solicitações pendentes na fila. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online-in-office-365"></a>Implantando a Conectividade Skype para o Skype for Business Online no Office 365

O recurso Conectividade Skype também faz parte do Skype for Business Online, que, por sua vez, faz parte do Office 365. Você pode habilitar a Conectividade Skype por meio do Centro de Administração do Skype for Business no portal do Office 365.
  
Para o Office 365 Midsize Business, o Office 365 Enterprise, o Office 365 Education e o Office 365 for Government: entre no portal do Office 365 e navegue até o Centro de Administração do Skype for Business. Vá para Comunicações Externas. Em Provedores de Serviços Públicos de Mensagens Instantâneas, clique em Habilitar. Se você quiser controlar o acesso de usuário individual a conectividade do Skype, você pode fazer isso por meio da edição configurações de comunicações externas de usuários individuais.
  
Para o Office 365 Small Business Premium: Entrar no Office 365 e vá até Admin \> configurações do serviço \> mensagens, as reuniões instantâneas e conferência. Ative as comunicações internas. As comunicações externas são ativadas na Conectividade Skype e nas comunicações com outras organizações que usam o Skype for Business.
  
Para obter mais informações sobre a administração do Skype for Business Online, consulte:
  
- [Permitir que os usuários entrem em contato com usuários externos do Skype for Business](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [O que tentar se você não pode IM Skype para negócios ou Skype contatos externos](https://support.office.com/en-us/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Adicionar um contato no Skype para negócios](https://support.office.com/en-US/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Administradores: Definir as configurações do Skype for Business para usuários individuais](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Implantando a conectividade do Skype para Skype para Business Server

Skype para Business Server usa a arquitetura de acesso de federação para oferecer suporte à conectividade com Skype. Essa conectividade permite que seus usuários do Skype for Business Server adicionem contatos do Skype. Os clientes do Skype também podem adicionar usuários do Skype for Business a suas listas de contatos. Com base em políticas definidas administrativamente no Skype para Business Server, os usuários serão capazes de se comunicar usando mensagens instantâneas, consulte presença uns dos outros e iniciar chamadas de áudio e vídeos. O recurso Conectividade Skype também está disponível no Skype for Business Online e pode ser habilitado para clientes do Centro de Administração do Skype for Business no portal do Office 365.
  
> [!NOTE]
> Se o Skype for Business Server já estiver configurado para conectar-se ao Windows Messenger usando PIC (conectividade a redes públicas de mensagens instantâneas), sua implantação já está configurada para a Conectividade Skype. A única mudança que você pode considerar é renomear sua entrada existente de PIC no Messenger como Skype.  
  
### <a name="accessing-the-skype-for-business-server-public-im-connectivity-provisioning-site-from-skype-for-business-server"></a>Acessando o Skype para provisionamento-site público de conectividade IM Business Server de Skype para Business Server

A conclusão desse processo de provisionamento pode levar até trinta dias ou levar apenas alguns dias, de acordo com o volume de solicitações. Recomendamos que você inicie esse processo primeiro, antes de realizar as demais etapas descritas neste documento. Depois que o processo de provisionamento do Skype for concluído para a sua conta, a conta será ativada e seus usuários elegíveis serão habilitados para conectividade a redes públicas de mensagens instantâneas.  
  
Para provisionar a Conectividade Skype, você precisa das seguintes informações:
  
- Número do contrato da Microsoft
    
- Nome de domínio totalmente qualificado (FQDN) do serviço de Borda de Acesso
    
- Domínios do protocolo SIP
    
- Qualquer FQDN adicional do serviço de Borda de Acesso
    
- Informações de contato
    
Para iniciar o processo de provisionamento para Conectividade Skype:
  
1. Entrar no site, https://pic.lync.com, usando o Microsoft Windows Live ID.
    
2. Selecione o tipo de contrato de licenciamento da Microsoft.
    
3. Marque a caixa de seleção, confirmando que você leu e aceita os Direitos de Uso do Produto do Skype for Business Server.
    
4. Na página Iniciar uma Solicitação de Provisionamento, clique no link apropriado para iniciar uma solicitação de provisionamento:
    
5. Na página Especificar Informações de Provisionamento, insira o FQDN do serviço de Borda de Acesso. Por exemplo, sip.contoso.com.
    
    > [!IMPORTANT]
    > A partir de 1º de julho de 2017, a Microsoft vai exigir, adicionalmente, que os clientes tenham o registro SRV DNS da Federação implantado para o funcionamento da conectividade a redes públicas de mensagens instantâneas.  
  
6. Insira pelo menos um ou mais nomes de domínio SIP e clique em Adicionar.
    
    > [!NOTE]
    > Pelo menos um servidor de Borda de Acesso é necessário para concluir o processo de provisionamento. Enquanto um único FQDN de Borda de Acesso pode oferecer suporte a vários domínios SIP, um único domínio SIP não pode ser representado por mais de um FQDN de Borda de Acesso. O domínio SIP e o servidor de Borda de Acesso devem estar ativos, em funcionamento e acessíveis na rede.              
  
7. Na lista de Provedores de Serviço Público de Mensagens Instantâneas, selecione Skype e clique em Avançar para adicionar informações de contato e enviar a solicitação de provisionamento.
    
Após o envio da solicitação de provisionamento, pode levar até 30 dias para a conta ser ativada e os usuários serem habilitados para Conectividade Skype, mas o processo pode levar apenas alguns dias, de acordo com a fila de solicitações.
  
### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Habilitando a federação e a PIC

Após o envio da solicitação de provisionamento, você pode concentrar-se nas tarefas administrativas e nas tarefas relacionadas ao ambiente do Skype necessárias para configurar a Conectividade Skype. Nesta seção, presumimos que o administrador implantou o Skype for Business Server e configurou o acesso externo, também conhecido como servidores de borda.  
  
Há três etapas principais necessárias para habilitar a federação e a PIC. São elas:
  
1. Configurar a federação e a PIC
    
2. Configurar pelo menos uma política para dar suporte ao acesso de usuários federados
    
3. Configurar a definição do provedor de PIC do Skype
    
#### <a name="1-configure-federation-and-pic"></a>1. Configurar a federação e a PIC

A federação é necessária para permitir que os usuários do Skype se comuniquem com os usuários do Skype for Business em sua organização. A PIC é uma classe de federação e deve ser configurada para permitir que seus usuários do Skype for Business se comuniquem com os usuários do Skype. A federação e a PIC são configuradas por meio do Painel de Controle do Skype for Business.
  
> [!NOTE]
> A federação de PIC não tem mais suporte no Live Communication Server 2005 SP1 e no Office Communications Server 2007. As plataformas com suporte para Federação PIC incluem Skype para Business Server, Lync Server 2013, Lync Server 2010 e Office Communications Server 2007 R2. 
  
A federação é necessária para permitir que os usuários do Skype se comuniquem com os usuários do Skype for Business em sua organização. A PIC é uma classe de federação e deve ser configurada para permitir que seus usuários do Skype for Business Server se comuniquem com os usuários do Skype. A federação e a PIC são configuradas por meio da caixa de diálogo de configuração de borda do Painel de Controle do Skype for Business, conforme mostra a figura.
  
![Definir Novo Pool de borda](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> Os atributos EnableSkypeIdRouting e EnableSkypeDirectorySearch devem ser definidos como true nas configurações de provedor público (consulte as instruções mais adiante) para que a pesquisa funcione. 
  
Isso conclui as tarefas administrativas que devem ser executadas no servidor. Agora você está pronto para a Conectividade Skype.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. configurar pelo menos uma política para suportar o acesso de usuário federado

Usando o Painel de Controle do Skype for Business Server, o administrador deve configurar uma ou mais políticas de acesso de usuário externo para controlar se os usuários do Skype podem colaborar com usuários internos do Skype for Business Server.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. configurar o provedor de Skype PIC configuração

Usando o Shell de Gerenciamento do Skype for Business Server, o administrador deve configurar a política de cliente do Skype for Business para exibir o Skype como um provedor de PIC adicional.  
  
> [!NOTE]
> Usuários dos provedores de serviços pública Instant Messaging Connectivity (PIC) não podem participar de mensagens Instantâneas ou conferências em sua organização, até que você também configurar pelo menos uma diretiva (etapa 2, anteriormente neste procedimento) para oferecer suporte à conectividade pública de IM. 
  
Para novas instalações, você pode configurar a Conectividade Skype ao habilitar o provedor público do Skype, por meio do Painel de Controle do Skype for Business Server, conforme mostra a figura.
  
![Provedores Federados SIP](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Para configurar a Conectividade Skype ao atualizar para o Skype for Business Server, você deve remover o provedor público existente do Skype e adicioná-lo novamente. 
  
Também é possível configurar a Conectividade Skype usando somente o PowerShell. Para configurar a Conectividade Skype usando o PowerShell:
  
1. Em um servidor front-end do Skype for Business Server, abra o Shell de Gerenciamento do Skype for Business Server.
    
2. Execute estes dois comandos:
    
   ```
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > Se você ainda não tem um provedor de PIC em seu ambiente e está criando um novo provedor de PIC, não é necessário executar o cmdlet Remove-CsPublicProvider.  
  
   ```
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    Qual é a função dos parâmetros menos óbvios?
    
   - ProxyFqdn: localização da borda de federação do Skype (própria/mantida pela Microsoft)
    
   - IconURL: ícone usado pelo Lync &amp; Skype para o cliente de negócios identificar visualmente os contatos do Skype
    
   - NameDecorationRoutingDomain e NameDecorationExcludedDomainList: configurá-los permite que os usuários insiram MSAs dos usuários do Skype sem precisar saber sobre "decorando" domínios de não-Microsoft com "msn.com". Isso elimina a necessidade de digitar "@msn.com (contoso.com) do usuário" para todos os domínios que não estão no ExcludedDomainList. O cliente SfB formatará automaticamente o MSA se o domínio NÃO estiver na lista de exclusões. Adicionamos os domínios mais comuns do Microsoft Account lista excluída.
    
     > [!NOTE]
     > Em caso de alterações, o provedor público deverá ser removido e um novo provedor deverá ser adicionado. Não é permitido fazer alterações in-loco. 
  
     > [!NOTE]
     > Adicionado ao Lync Server 2013 CU5 &amp; a situação onde adicionar contatos do Skype necessárias para os usuários do Lync "decoram" domínios de não-Microsoft para melhorar o cliente de desktop do Lync no Office 2013 SP1, NameDecorationRoutingDomain and NameDecorationExcludedDomainList identificar e roteá-los para Skype (o formato dos: user(contoso.com)@msn.com). Essas novas configurações permitirá a formatação automática do usuário endereço enter na caixa de diálogo "Adicionar contato Skype" com o NameDecorationRoutingDomain (que deve ser definida como msn.com) se ele não contiver os domínios no (NameDecorationExcludedDomainList Estamos atualmente pode suportar msn.com, live.com, Hotmail.com, outlook.com). 
  
3. Agora, a partir de um cliente Skype for Business, os usuários podem pesquisar e adicionar usuários do Skype.
    
## <a name="clients-and-interoperability-matrix"></a>Clientes e matriz de interoperabilidade

A tabela a seguir descreve o status de interoperabilidade entre a versão mais recente do consumidor do Skype e a versão mais recente do Skype for Business.
  

|**Clientes Skype**|**Adicionar contatos, IM, presença, chamada de áudio e vídeo**|**Comentário**|
|:-----|:-----|:-----|
|Skype Windows Desktop  <br/> |7.6 ou superior, Windows XP ou superior  <br/> |**NEW**: adicionado suporte para o cliente do Skype do Windows em execução no Windows XP e Windows Vista **(requer a versão mais recente do cliente 7.26 ou superior)** <br/> |
|Skype Mobile- telefone Android e Tablet   <br/> |6.19 ou superior, executando o Sistema Operacional do Android versão 4.0.3 ou superior  <br/> |Dispositivos de baixa especificação podem não suportar chamada de vídeo  <br/> |
|Skype Mobile - iOS  <br/> |6.11 ou superior, em IOS 7 ou superior  <br/> |Não compatível com iPhone 4 e anteriores, iPod quarta geração e anteriores, iPad primeira geração  <br/> |
|Skype Mac  <br/> |7.19 ou superior, no Mac OS X 10.9 (Mavericks) ou superior  <br/> |Requer Mac OSX 10.9 ou superior  <br/> |
|Área de trabalho e celular do Aplicativo Universal Windows para Skype (Windows 10)  <br/> |Windows 10 (Redstone 1 atualizado ou posterior)  <br/> |O aplicativo universal do Windows receberá uma atualização no terceiro trimestre de 2016, quando será adicionado suporte para interoperabilidade  <br/> |
   
A tabela a seguir descreve o status de interoperabilidade entre a versão mais recente do Skype for Business e a versão mais recente do consumidor do Skype.  
  
|**Cliente**|**Pesquisa de diretórios do Skype e Adicionar contatos**|**Interop de áudio e vídeo e mensagens instantâneas do Skype**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |Sim   <br/> |Sim   <br/> |
|Skype for Business para Mac  <br/> |É possível adicionar (sem pesquisa)  <br/> |Sim  <br/> |
|Lync Desktop 2013  <br/> |É possível adicionar (sem pesquisa)  <br/> |Sim  <br/> |
|Lync Web App – online e local  <br/> |N/D  <br/> |N/D  <br/> |
|Lync Mobile – Windows Phone  <br/> |Em breve  <br/> |Sim  <br/> |
|Lync Mobile – Android  <br/> |Em breve  <br/> |Sim  <br/> |
|Lync Mobile – iOS  <br/> |Em breve  <br/> |Sim  <br/> |
|Sistema de Salas do Lync  <br/> |Em breve  <br/> |Sim  <br/> |
|Lync Modern App (Win 8.1)  <br/> |Sim  <br/> |Sim   <br/> |
|Lync Mac 2011  <br/> |É possível adicionar (sem pesquisa)  <br/> |Sim  <br/> |
|Lync Desktop 2010  <br/> |É possível adicionar (sem pesquisa)  <br/> |Sim  <br/> |
|Lync Phone Edition  <br/> |N/D  <br/> |N/D  <br/> |
|Lync Attendant  <br/> |N/D  <br/> |N/D  <br/> |
   

