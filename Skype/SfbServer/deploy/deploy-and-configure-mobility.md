---
title: Implantar e configurar o Mobility para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: Este artigo irá orientá-lo nas etapas para configurar uma instalação existente do Skype for Business Server para usar o serviço de mobilidade, permitindo que os dispositivos móveis aproveitem os recursos de mobilidade do Skype for Business Server.
ms.openlocfilehash: 457eeff39c87f20326d64cc5227745b43e0af5f8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029062"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>Implantar e configurar o Mobility para o Skype for Business Server  
 
Este artigo irá orientá-lo nas etapas para configurar uma instalação existente do Skype for Business Server para usar o serviço de mobilidade, permitindo que os dispositivos móveis aproveitem os recursos de mobilidade do Skype for Business Server.
  
Revisou o artigo [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) , você deve estar pronto para prosseguir com as etapas abaixo para implantar a mobilidade no seu ambiente do Skype for Business Server. As etapas são as seguintes (e estamos incluindo nesta tabela uma lista de permissões):
  
|**Fase**|**Permissões**|
|:-----|:-----|
|[Criar registros DNS](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |Admins. do Domínio  <br/> DNSAdmins  <br/> |
|[Modificar certificados](deploy-and-configure-mobility.md#ModCerts) <br/> |Administrador Local  <br/> |
|[Configurar o proxy inverso](deploy-and-configure-mobility.md#ConfigRP) <br/> |Administrador Local  <br/> |
|[Configurar descoberta automática para mobilidade com implantações híbridas](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Admins. do Domínio  <br/> |
|[Testar sua implantação de mobilidade](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[Configurar para notificações por push](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[Configurar a política de mobilidade](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
Todas as seções a seguir contêm etapas que pressupõem que você leu o tópico de planejamento. Se alguma coisa for confusa, sinta-se à vontade para fazer o check-out das informações.

> [!NOTE]
> O suporte do MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para suportar mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdados que usam o MCX precisarão atualizar para um cliente atual.
  
## <a name="create-dns-records"></a>Criar registros DNS
<a name="CreateDNSRec"> </a>

Talvez você já tenha isso como parte do seu ambiente do Skype for Business Server, mas é necessário criar os seguintes registros para que a descoberta automática funcione:
  
- Um registro DNS interno para dar suporte a usuários móveis que estão se conectando dentro da rede da sua organização.
    
- Um registro DNS externo (ou público) para dar suporte a usuários móveis que estão se conectando de fora da rede da sua organização.
    
Esses registros podem ser nomes de (host) ou registros CNAME (você não precisa fazer os dois, estamos apenas incluindo as etapas para tudo aqui).
  
### <a name="create-an-internal-dns-cname-record"></a>Criar um registro CNAME de DNS interno

1. Faça logon em um servidor DNS de sua rede que seja membro do grupo **Administradores de domínio** ou do grupo **DNSAdmins** .
    
2. Clique em **Iniciar**, escolha **Ferramentas administrativas** (talvez seja necessário **procurá** -lo se não houver uma opção no menu Iniciar) e, em seguida, clique em **DNS** para abrir o snap-in administrativo do DNS.
    
3. No painel esquerdo da janela do console, você precisará ir para o domínio que está em casa para os servidores front-end do Skype for Business Server e expandir as **zonas de pesquisa direta** .
    
4. Reserve um tempo para ver qual dos seguintes itens você tem:
    
   - Qualquer registro de host A ou AAAA do servidor front-end (Standard ou Enterprise) ou pools de front-ends.
    
   - Todos os registros de host A ou AAAA de um diretor ou pool de diretores (uma configuração opcional que você pode ter em sua implantação).
    
5. Depois de observar isso, clique com o botão direito do mouse no nome do domínio SIP e escolha **novo alias (CNAME)** no menu.
    
6. Na caixa de texto **nome do alias** , digite lyncdiscoverinternal para o nome do host, para a URL interna do serviço de descoberta automática.
    
7. No **nome de domínio totalmente qualificado (FQDN para o host de destino**, você precisará digitar ou procurar o FQDN de serviços Web internos para o seu pool de front-ends (ou servidor de front-end único, ou o pool de diretores ou diretor), identificado na etapa 4 acima. Clique em OK quando for inserido.
    
8. Você precisará criar um novo registro CNAME de descoberta automática na zona de pesquisa direta para cada domínio SIP suportado em seu ambiente do Skype for Business Server.
    
### <a name="create-an-external-dns-cname-record"></a>Criar um registro CNAME de DNS externo

1. Essas etapas são genéricas, porque não podemos saber qual provedor de DNS público você pode estar usando, mas ainda queremos ajudá-lo. Conecte-se ao seu provedor de DNS público com uma conta que possa criar novos registros DNS.
    
2. Nesse momento, um domínio SIP já deve existir para o Skype for Business Server. Expanda a **zona de pesquisa direta** para este domínio SIP ou abra-a.
    
3. Reserve um tempo para ver qual dos seguintes itens você tem:
    
   - Qualquer registro de host A ou AAAA do servidor front-end (Standard ou Enterprise) ou pools de front-ends.
    
   - Todos os registros de host A ou AAAA de um diretor ou pool de diretores (uma configuração opcional que você pode ter em sua implantação).
    
4. Depois de ter essas informações, você poderá selecionar uma opção para criar um **novo alias (CNAME)**.
    
5. Agora você pode digitar um **nome de alias**, é necessário inserir lyncdiscover aqui para a URL externa do serviço de descoberta automática.
    
6. Em seguida, deve haver uma área para inserir um **FQDN para o host de destino**, que deverá ser o FQDN do seu pool de front-ends (ou servidor front-end único ou o pool ou diretor do diretor), identificado na etapa 3 acima.
    
7. Talvez seja necessário salvar aqui ou, se você precisar criar registros CNAME adicionais na zona de pesquisa direta de cada domínio SIP no seu ambiente do Skype for Business Server, você deve fazer isso, mas quando estiver pronto, salve o seu trabalho.
    
### <a name="create-an-internal-dns-a-record"></a>Criar um registro de DNS interno

1. Faça logon em um servidor DNS de sua rede que seja membro do grupo **Administradores de domínio** ou do grupo **DNSAdmins** .
    
2. Clique em **Iniciar**, escolha **Ferramentas administrativas** (talvez seja necessário **procurá** -lo se não houver uma opção no menu Iniciar) e, em seguida, clique em **DNS** para abrir o snap-in administrativo do DNS.
    
3. No painel esquerdo da janela do console, você precisará ir para o domínio que está em casa para os servidores front-end do Skype for Business Server e expandir as **zonas de pesquisa direta** .
    
4. Reserve um tempo para ver qual dos seguintes itens você tem:
    
   - Qualquer registro de host A ou AAAA do servidor front-end (Standard ou Enterprise) ou pools de front-ends.
    
   - Todos os registros de host A ou AAAA de um diretor ou pool de diretores (uma configuração opcional que você pode ter em sua implantação).
    
5. Depois de observar isso, clique com o botão direito do mouse no nome do domínio SIP e escolha **novo host (A ou aaaa)** no menu.
    
6. Na caixa de texto **nome** , digite lyncdiscoverinternal para o nome do host, para a URL interna do serviço de descoberta automática.
    
7. Na caixa de texto **endereço IP** , digite o endereço IP dos serviços Web internos para seu pool de front-ends (ou servidor front-end único, ou o pool de diretores ou diretor), identificado na etapa 4 acima.
    
8. Quando isso estiver concluído, clique em **Adicionar host**e, em seguida, clique em **OK**.
    
9. Você precisará criar um novo registro de descoberta automática ou registros AAAA na zona de pesquisa direta para cada domínio SIP suportado no seu ambiente do Skype for Business Server. Para fazer isso, repita as etapas 6-8 quantas vezes forem necessárias.
    
10. Quando terminar, clique em **concluído**.
    
### <a name="create-an-external-dns-a-record"></a>Criar um registro de DNS externo

1. Essas etapas são genéricas, porque não podemos saber qual provedor de DNS público você pode estar usando, mas ainda queremos ajudá-lo. Conecte-se ao seu provedor de DNS público com uma conta que possa criar novos registros DNS.
    
2. Nesse momento, um domínio SIP já deve existir para o Skype for Business Server. Expanda a **zona de pesquisa direta** para este domínio SIP ou abra-a.
    
3. Reserve um tempo para ver qual dos seguintes itens você tem:
    
   - Qualquer registro de host A ou AAAA do servidor front-end (Standard ou Enterprise) ou pools de front-ends.
    
   - Todos os registros de host A ou AAAA de um diretor ou pool de diretores (uma configuração opcional que você pode ter em sua implantação).
    
4. Depois de ter essas informações, você poderá selecionar uma opção para criar um **novo host a ou aaaa**.
    
5. Agora você deve ser capaz de inserir um **nome**, você precisa inserir lyncdiscover aqui para a URL externa do serviço de descoberta automática.
    
6. Em seguida, deve haver uma área para inserir em um **endereço IP**, será necessário ser o IP para seu pool de front-ends (ou servidor front-end único ou o pool ou diretor de diretor), identificado na etapa 3 acima.
    
7. Talvez seja necessário salvar aqui ou se você precisar criar registros A ou AAAA adicionais na zona de pesquisa direta de cada domínio SIP para seu ambiente do Skype for Business Server, você deve fazer isso, mas quando estiver pronto, salve o seu trabalho.
    
## <a name="modify-certificates"></a>Modificar certificados
<a name="ModCerts"> </a>

Se você tiver dúvidas sobre o planejamento de certificados, documentamos isso em nosso artigo [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) . Depois de revisar isso, vamos orientá-lo no seguinte:
  
- Preciso de novos certificados?
    
- Solicitação de novos certificados da autoridade de certificação (AC).
    
- Atualização de seus certificados in-loco com as substituições usando o PowerShell.
    
- Verificar os certificados usando o snap-in de certificados no console de gerenciamento Microsoft (MMC).
    
### <a name="do-i-need-new-certificates"></a>Preciso de novos certificados?

1. Primeiro, talvez seja necessário verificar e ver quais certificados estão no local e se eles têm ou não as entradas de que você precisa. Para fazer isso, você precisará fazer logon no Skype for Business Server com uma conta que seja um administrador local. Essa conta também pode precisar ter direitos para a autoridade de certificação (CA) de emissão, para algumas dessas etapas.
    
2. Abra o Shell de gerenciamento do Skype for Business Server (você pode usar a pesquisa para encontrá-la se não a tiver fixada no menu iniciar ou na barra de tarefas).
    
3. Será essencial que você saiba quais certificados foram atribuídos antes de tentar adicionar um certificado atualizado. Portanto, no comando, digite:
    
   ```powershell
   Get-CsCertificate
   ```

4. As informações da etapa 3 serão exclusivas para você. Você precisará procurá-lo para determinar se você tem um único certificado que tenha sido atribuído para várias coisas ou se você tem um certificado diferente atribuído aos diferentes componentes que precisam deles. O parâmetro **use** informará como um certificado está sendo usado, e o parâmetro **Thumbprint** informará se é todo o mesmo certificado ou vários certificados.
    
5. Se você tiver as entradas de SAN recomendadas em nossa seção de planejamento, você está bom. Caso contrário, você precisará solicitar um novo certificado ou vários certificados (dependendo da sua configuração) da autoridade de certificação.
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>Solicitar um novo certificado ou certificados da autoridade de certificação (CA)

1. Depois de verificar quais entradas de SAN você tem, você sabe que tem um **único certificado** (após verificar as etapas acima) e aprendeu que não tem todas as entradas necessárias. Uma nova solicitação de certificado precisa ser feita à sua autoridade de certificação. Abra seu PowerShell do Skype for Business Server:
    
   - Para uma SAN de serviço de descoberta automática ausente (substituindo o parâmetro-CA pelo caminho de sua própria autoridade de certificação):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Agora, se você tiver vários domínios SIP, não será possível usar o parâmetro AllSipDomain como no exemplo acima. Em vez disso, você precisará usar o parâmetro DomainName. E quando você usa o parâmetro DomainName, você precisa definir o FQDN para os registros lyncdiscoverinternal e lyncdiscover. Um exemplo seria (substituindo o parâmetro-CA pelo caminho de sua própria autoridade de certificação):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. Ou, depois de verificar quais entradas de SAN você tem, você descobriu que tem **vários certificados** que não possuem todas as entradas necessárias. Uma nova solicitação de certificado precisa ser feita à sua autoridade de certificação. Abra seu PowerShell do Skype for Business Server:
    
   - Para uma SAN de serviço de descoberta automática ausente (substituindo o parâmetro-CA pelo caminho de sua própria autoridade de certificação):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Agora, se você tiver vários domínios SIP, não será possível usar o parâmetro AllSipDomain como no exemplo acima. Em vez disso, você precisará usar o parâmetro DomainName. E quando você usa o parâmetro DomainName, você precisa definir o FQDN para os registros lyncdiscoverinternal e lyncdiscover. Os exemplos seriam (substituindo o parâmetro-CA pelo caminho de sua própria autoridade de certificação):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - Depois que os novos certificados tiverem sido gerados pela autoridade de certificação, você precisará atribuí-los.
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>Atribuir certificados usando o Shell de gerenciamento do Skype for Business Server

- Dependendo do que você encontrar na seção eu preciso de novas certificações, você precisará executar **um** dos seguintes procedimentos.
    
  - Se você tiver um único certificado para tudo (as impressões digitais são idênticas), será necessário executar o seguinte:
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - Se você tiver certificados diferentes para as coisas (as impressões digitais são diferentes), execute isto em vez disso:
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>Exibindo certificados no console de gerenciamento Microsoft (MMC)

1. Você tem uma opção para examinar seus certificados usando o snap-in de certificados para o MMC. Basta digitar MMC na pesquisa e ele deverá aparecer como uma opção de aplicativo.
    
2. Para adicionar o snap-in certificados, você precisará clicar em **arquivo**e **Adicionar/remover snap-in...** (ou atalho de teclado **Ctrl + M** também funcionará). **Certificados** será uma opção no painel esquerdo, selecione-o e, em seguida, **conta de computador** na janela pop-up e, em seguida, clique em **Avançar**.
    
3. Ainda na janela pop-up, em todas as chances de que você esteja fazendo isso no computador em que você está em casa para os certificados que precisa examinar, deixe a seleção no **computador local** se isso for possível. Se você estiver trabalhando em um computador remoto, altere o botão de opção para **outro computador** e, em seguida, insira o FQDN desse computador ou use o botão **procurar** para pesquisar o computador pelo AD. Depois de selecionar o computador, você precisará clicar em **concluir** quando estiver pronto e, em seguida, em **OK** para adicionar o snap-in ao MMC.
    
4. Expanda a seção **certificados** no painel esquerdo do MMC. Expanda também a pasta **pessoal** e, em seguida, selecione **certificados**. Isso permite que você veja os certificados nesse repositório.
    
5. Você precisa localizar o certificado que deseja exibir, clicar com o botão direito do mouse nele e escolher **abrir**.
    
    > [!NOTE]
    > Como saber qual é o certificado? Deve ser o único certificado atribuído a tudo para o seu farm, ou você pode ter vários certificados para diferentes coisas, como padrão, serviços Web internos, etc., e, nesse caso, talvez seja necessário examinar vários certificados. Vários certificados terão a mesma impressão digital. 
  
6. Depois de obter o modo de exibição de **certificado** , escolha **detalhes**. Isso permitirá que você veja o nome da entidade do certificado quando você selecionar **assunto**e o nome de entidade atribuído e as propriedades associadas serão exibidos.
    
7. Você também precisará verificar as entradas de **nome alternativo de entidade** . Você encontrará uma ou mais das seguintes opções:
    
   - O nome do pool para este pool ou o nome do servidor único, se não for um pool.
    
   - O nome do servidor ao qual o certificado está atribuído.
    
   - Registros de URL simples, normalmente atendem e são de discagem.
    
   - Nomes internos e externos de serviços Web (por exemplo, webpool01.contoso.net, webpool01.contoso.com), com base nas escolhas feitas no construtor de topologias e nas seleções de serviços Web do nas.
    
   - Se já tiver sido atribuído, o lyncdiscover. \<sipdomain\> e lyncdiscoverinternal. \<sipdomain\> registros.
    
     Você precisará verificar vários certificados se tiver mais de um atribuído (verifique a observação acima).
    
8. Portanto, se você encontrar lyncdiscover. \<sipdomain\> e lyncdiscoverinternal. \<sipdomain\> registros, você já configurou isso. Você pode fechar o MMC.
    
9. Se não forem atribuídas, será necessário fazer uma nova solicitação de certificado (descrita acima) ou você precisará instalar as solicitações post-Request (recomendamos o seguinte para o PowerShell acima).
    
## <a name="configure-the-reverse-proxy"></a>Configurar o proxy inverso
<a name="ConfigRP"> </a>

As etapas abaixo não devem ser seguidas exatamente. Isso acontece porque nas versões anteriores do produto, gostaríamos de orientá-lo, por exemplo, a configuração da TMG (Threat Management Gateway) e, se você não o estivesse usando, precisará trabalhar com sua própria versão.
  
A TMG não está mais sendo oferecida pela Microsoft como um produto e, se ainda precisar configurá-la, você poderá examinar as [etapas do Lync Server 2013](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx). Mas as informações a seguir devem ser mais úteis em geral, mesmo se não houver nenhuma forma de fornecer etapas específicas passo a passo para cada proxy reverso.
  
Temos duas coisas principais a considerar:
  
- Você vai fazer a solicitação de descoberta automática inicial por HTTPS (o que recomendamos)?
    
  - Se você tiver uma regra de publicação na Web, precisará modificá-la.
    
  - Se você ainda não tem uma regra de publicação na Web, precisa criá-la.
    
- Se você estiver fazendo uma solicitação de descoberta automática inicial por HTTP, você também precisará criar ou modificar essa regra.
    
> [!NOTE]
> **Importante** Um valor de tempo limite de proxy é um número que varia de implantação para implantação. Você deve monitorar sua implantação e modificar o valor da melhor experiência para os clientes. É possível definir o valor como baixo como 200. Se você estiver dando suporte a clientes móveis do Lync em seu ambiente, você deve definir o valor como 960 para permitir o tempo limite de notificação por push do Office 365, que tem um valor de tempo limite de 900. É muito provável que você tenha que aumentar o valor de tempo limite para evitar que o cliente seja desconectado quando o valor for muito baixo ou diminuir o número se as conexões por meio do proxy não forem desconectadas, mas muito longo após o cliente ter sido desconectado. O monitoramento e a determinação de desempenho mais comuns para seu ambiente é a única maneira precisa de determinar a configuração apropriada para esse valor.
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>Modificar a regra de publicação da Web existente para sua SAN e URL de descoberta automática externa

1. Abra sua interface de proxy reverso.
    
2. Você precisará localizar sua regra de publicação na Web e escolher a opção Editar (ela pode estar em um menu ou em uma guia, dependendo da sua configuração de proxy reverso).
    
3. Deve haver uma área à qual essa regra de publicação da Web seja aplicada. Você precisa modificar essa regra para sites de entrada ou solicitações de sites. Você **adicionará** uma nova entrada.
    
4. Digite o nome do seu site de descoberta automática (o exemplo que usaremos é lyncdiscover.contoso.com) e clique em **OK** ou **salvar**, dependendo do seu formato de proxy reverso.
    
5. Você pode ter um novo certificado que tenha a entrada de SAN de descoberta automática. Isso também precisa ser instalado e configurado para uso de acordo com as configurações do seu proxy reverso. Certifique-se de salvar tudo quando a configuração for concluída.
    
6. Se o seu proxy reverso tiver uma funcionalidade de **teste** , use-o para garantir que tudo está funcionando corretamente.
    
7. Agora, talvez seja necessário repetir essas etapas se você tiver um diretor ou um pool de diretores no seu ambiente (isso significa que você tem uma segunda regra).
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Criar uma regra de publicação na Web para a URL externa de descoberta automática

1. Abra sua interface de proxy reverso.
    
2. Você precisará localizar onde na interface você cria suas regras de publicação na Web e escolher a opção **novo** ou **criar** (pode estar em um menu ou guia, dependendo da sua configuração de proxy reverso). Você está procurando a opção de criar uma nova regra de publicação na Web.
    
3. Normalmente, você precisará inserir as seguintes informações:
    
   - **Nome**: o nome da regra
    
   - **Ação de regra**: nesse caso, é uma regra de **permissão** , você está permitindo que algo passe pelo seu proxy reverso.
    
   - A regra de **publicação** ou opção que você está escolhendo seria **um único site ou balanceador de carga**.
    
   - Isso precisa ser **SSL** para acesso externo, escolha essa opção.
    
   - Você precisará publicar um caminho para **publicação interna**e inserir o FQDN para os serviços Web externos no balanceador de carga do pool de front-ends (ou o FQDN do balanceador de carga do pool de diretores, se tiver um), um exemplo seria sfb_pool01. contoso. local.
    
   - Você deve digitar ** / *** como o caminho a ser publicado, mas você também precisa **encaminhar o cabeçalho de host original**.
    
   - Haverá uma opção para detalhes ou informações de **nome público ou externo** . Este é o local onde você poderá inserir:
    
   - **Aceitar solicitações**, mas deve ser para o nome de domínio.
    
   - Para o **nome**, você deve inserir **lyncdiscover.** <sipdomain>(esta é a URL externa do serviço de descoberta automática). Agora, se você estiver criando uma regra para a URL de serviços Web externos no pool de front-ends, precisará digitar o FQDN dos serviços Web externos em seu pool de front-ends (por exemplo, lyncwebextpool01.contoso.com).
    
   - Haverá uma opção de **caminho** , e você precisará inserir ** / *** aqui.
    
   - Você precisará selecionar um **ouvinte SSL** com seu certificado público atualizado.
    
   - A **delegação de autenticação** deve ser definida como **sem delegação**, mas a autenticação direta do cliente **deve** ser permitida.
    
   - A regra deve ser definida para **todos os usuários**.
    
   - Isso deve ser todas as informações necessárias para criar essa regra e permitir que você continue.
    
4. Você precisará garantir que o **cabeçalho do host original** seja encaminhado.
    
5. As portas do **servidor Web** também precisarão ser definidas, você precisará fazer o seguinte:
    
   - **Redirecionar solicitações para a porta http** e o número da porta deverá ser **8080**.
    
   - **Redirecione as solicitações para a porta SSL** e o número da porta deve ser **4443**.
    
6. Quando tudo estiver configurado, você precisará salvá-los ou aplicá-los e, em seguida, poderá testar a regra.
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>Criar uma regra de publicação na Web para a porta 80 (opcional)

1. Abra sua interface de proxy reverso.
    
2. Você precisará localizar onde na interface você cria suas regras de publicação na Web e escolher a opção **novo** ou **criar** (pode estar em um menu ou guia, dependendo da sua configuração de proxy reverso). Você está procurando a opção de criar uma nova regra de publicação na Web.
    
3. Normalmente, você precisará inserir as seguintes informações:
    
   - **Nome**: o nome da regra
    
   - **Ação de regra**: nesse caso, é uma regra de **permissão** , você está permitindo que algo passe pelo seu proxy reverso.
    
   - A regra de **publicação** ou opção que você está escolhendo seria **um único site ou balanceador de carga**.
    
   - Isso precisa ser uma **conexão não segura para se conectar ao servidor Web ou ao farm publicado**.
    
   - Você precisará publicar um caminho para **publicação interna**e inserir o FQDN para o **endereço VIP** do balanceador de carga do seu pool de front-ends, um exemplo seria sfb_pool01. contoso. local.
    
   - Você deve digitar ** / *** como o caminho a ser publicado, mas você também precisa **encaminhar o cabeçalho de host original**.
    
   - Haverá uma opção para detalhes ou informações de **nome público ou externo** . Este é o local onde você poderá inserir:
    
   - **Aceitar solicitações**, mas deve ser para o nome de domínio.
    
   - Para o **nome**, você deve inserir **lyncdiscover.** <sipdomain>(esta é a URL externa do serviço de descoberta automática).
    
   - Haverá uma opção de **caminho** , e você precisará inserir ** / *** aqui.
    
   - Você precisará selecionar um ouvinte da Web ou permitir que seu proxy reverso crie um para você.
    
   - A **delegação de autenticação** deve ser definida como **sem delegação**, mas a autenticação direta do cliente **não deve** ser permitida.
    
   - A regra deve ser definida para **todos os usuários**.
    
   - Isso deve ser todas as informações necessárias para criar essa regra e permitir que você continue.
    
4. As portas de **servidor Web** precisarão ser definidas, será necessário fazer o seguinte:
    
   - **Redirecionar solicitações para a porta http** e o número da porta deverá ser **8080**.
    
   - **Redirecione as solicitações para a porta SSL** e o número da porta deve ser **4443**.
    
5. Quando tudo estiver configurado, você precisará salvá-los ou aplicá-los e, em seguida, poderá testar a regra.
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>Configurar descoberta automática para mobilidade com implantações híbridas
<a name="ConfigAutoD"> </a>

Ambientes híbridos no Skype for Business Server são ambientes que combinam um ambiente local e do O365. Quando o Skype for Business Server funciona em um ambiente híbrido, o serviço de descoberta automática precisa ser capaz de localizar um usuário a partir de qualquer um desses ambientes.
  
Para permitir que clientes móveis descubram onde um usuário está localizado, o serviço de descoberta automática precisa ser configurado com um novo Uniform Resource Locator (URL). As etapas são:
  
1. Abra o Shell de gerenciamento do Skype for Business Server.
    
2. Execute o seguinte para obter o valor do atributo **ProxyFQDN** para o seu ambiente do Skype for Business Server:
    
   ```powershell
   Get-CsHostingProvider
   ```

3. Em seguida, ainda na janela do Shell, execute:
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    Onde [identidade] é substituído pelo nome do domínio do espaço de endereço SIP compartilhado.
    
## <a name="test-your-mobility-deployment"></a>Testar sua implantação de mobilidade
<a name="TestMobility"> </a>

Depois de implantar o serviço de mobilidade do Skype for Business Server e o serviço de descoberta automática do Skype for Business Server, convém executar uma transação de teste para garantir que o direito de trabalho da sua implantação. Você pode executar **Test-CsUcwaConference** para testar a capacidade de dois usuários criarem, ingressar e se comunicar em uma conferência. Você precisará de dois usuários (real ou teste) e de suas credenciais completas para fazer este teste. Este comando funcionará para clientes do Skype for Business, bem como para os clientes do Lync Server 2013.
  
Para clientes do Lync Server 2010 no Skype for Business Server 2015, você precisará executar **Test-CsMcxP2PIM** para testar. Seus usuários do Lync Server 2010 ainda terão que ser usuários reais ou usuários de teste predefinidos, e você precisará de suas credenciais de senha.

> [!NOTE]
> O suporte do MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para suportar mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdados que usam o MCX precisarão atualizar para um cliente atual.
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>Testar a conferência para clientes móveis do Skype for Business e do Lync 2013

1. Faça logon como membro da função **CsAdministrator** em qualquer computador onde o **Shell de gerenciamento do Skype for Business Server** e o **OCScore** estejam instalados.
    
2. Inicie o **Shell de gerenciamento do Skype for Business Server** (você pode digitar o nome na pesquisa ou ir para **todos os programas** e escolha-o).
    
3. Na linha de comando, digite:
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   Também é possível definir credenciais em um script e passá-las para o cmdlet Test. Temos um exemplo disso abaixo.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>Testar a conferência para clientes móveis do Lync 2010

> [!NOTE]
> O suporte do MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para suportar mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdados que usam o MCX precisarão atualizar para um cliente atual.

1. Faça logon como membro da função **CsAdministrator** em qualquer computador onde o **Shell de gerenciamento do Skype for Business Server** e o **OCScore** estejam instalados.
    
2. Inicie o **Shell de gerenciamento do Skype for Business Server** (você pode digitar o nome na pesquisa ou ir para **todos os programas** e escolha-o).
    
3. Na linha de comando, digite:
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   Também é possível definir credenciais em um script e passá-las para o cmdlet Test. Temos um exemplo disso abaixo.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

Para examinar os procedimentos de comando mais tarde, confira [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) e [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).
  
## <a name="configure-for-push-notifications"></a>Configurar para notificações por push
<a name="ConfigPush"> </a>

As notificações por push, na forma de selos, ícones ou alertas, podem ser enviadas para um dispositivo móvel, mesmo quando o aplicativo Skype ou Lync está inativo. Mas o que são notificações por push? Eles são alertas de eventos, como um convite de IM novo ou perdido ou para uma caixa postal recebida. O serviço de mobilidade do Skype for Business Server envia essas notificações para o serviço de notificação por push do Skype for Business Server baseado na nuvem, que envia as notificações para o serviço de notificação por push da Microsoft (MSNS) para usuários do Windows Phone.
  
Essa funcionalidade não é alterada no Lync Server 2013, mas se você tiver um Skype for Business Server, será necessário fazer o seguinte:
  
- Para um servidor de borda do Skype for Business Server, adicione um novo provedor de hospedagem, o Microsoft Skype for Business Online e configure a Federação do provedor de hospedagem entre sua organização e o Skype for Business online.
    
- Habilite notificações por push executando o cmdlet **set-CsPushNotificationConfiguration** . Por padrão, as notificações por push estão desativadas.
    
- Teste sua configuração de Federação e as notificações por push.
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>Configurar o servidor de borda do Skype for Business para notificações por push

1. Faça logon, com uma conta que seja membro da função **CsAdministrator** , para um computador onde o **Shell de gerenciamento do Skype for Business Server** e o **OCScore** estão instalados.
    
2. Inicie o **Shell de gerenciamento do Skype for Business Server**.
    
3. Adicionar um provedor de hospedagem online do Skype for Business Server.
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   Como exemplo:
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > Você não pode ter mais de uma relação de Federação com um único provedor de hospedagem. Portanto, se você já configurou um provedor de hospedagem que tem uma relação de Federação com o sipfed.online.lync.com, não adicione outro provedor de hospedagem para ele, mesmo que a identidade do provedor de hospedagem seja algo diferente de SkypeOnline. 
  
4. Configure a Federação do provedor de hospedagem entre sua organização e o serviço de notificação por push no Skype for Business online. Na linha de comando, você precisará digitar:
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>Habilitar notificações por push

1. Faça logon, com uma conta que seja membro da função **CsAdministrator** , para um computador onde o **Shell de gerenciamento do Skype for Business Server** e o **OCScore** estão instalados.
    
2. Inicie o **Shell de gerenciamento do Skype for Business Server**.
    
3. Habilitar notificações por push:
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. Habilitar Federação:
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>Testar a Federação e as notificações por push

1. Faça logon, com uma conta que seja membro da função **CsAdministrator** , para um computador onde o **Shell de gerenciamento do Skype for Business Server** e o **OCScore** estão instalados.
    
2. Inicie o **Shell de gerenciamento do Skype for Business Server**.
    
3. Teste a configuração da Federação:
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    Como exemplo:
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. Teste suas notificações por push:
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    Como exemplo:
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a>Configurar a política de mobilidade
<a name="ConfigMob"> </a>

Você tem a capacidade com o Skype for Business Server determinar quem pode usar seu serviço de mobilidade, ligar via trabalho, VoIP (voz sobre IP) ou vídeo, bem como se o WiFi será necessário para VoIP ou vídeo. Call via trabalho permite que um usuário móvel use seu número de telefone comercial, em vez do número de telefone celular, ao colocar e receber chamadas. A pessoa na outra extremidade da linha não verá o número de telefone celular do usuário móvel e permitirá que o usuário móvel Evite encargos de chamadas de saída. Quando VoIP e vídeo são configurados, os usuários podem tomar e fazer chamadas VoIP e vídeo. As configurações para o uso de WiFi determinam se o dispositivo móvel de um usuário será necessário para usar uma rede WiFi em uma rede de dados da rede celular.
  
Mobilidade, ligar via trabalho e VoIP e recursos de vídeo são habilitados por padrão. A configuração para exigir WiFi para VoIP e vídeo está desabilitada. Um administrador tem a capacidade de alterar isso de forma global, por site ou por usuário.
  
Para poder usar os recursos de mobilidade e ligar via trabalho, os usuários precisam ser:
  
- Habilitado para o Skype for Business Server
    
- Habilitado para o Enterprise Voice.
    
- Atribuída uma política de mobilidade que tem a opção **EnableMobility** definida como **true**.
    
Para que os usuários possam usar a chamada via trabalho, eles também precisarão ser:
  
- Atribuída uma política de voz que tem a opção **habilitar toque simultâneo de telefones** selecionada.
    
- Atribuída uma política de mobilidade que tem o **EnableOutsideVoice** definido como **true**.
    
> [!NOTE]
> Os usuários que não estão habilitados para o Enterprise Voice podem usar seus dispositivos móveis para fazer chamadas do Skype para Skype VoIP ou ingressar em conferências usando o link Clique para entrar em seus dispositivos móveis, se as opções apropriadas estiverem definidas para a política de voz que estão associadas com. Há mais detalhes no tópico planejamento. 
  
### <a name="modify-global-mobility-policy"></a>Modificar a política de mobilidade global

1. Faça logon, com uma conta que seja membro da função **CsAdministrator** , para um computador onde o **Shell de gerenciamento do Skype for Business Server** e o **OCScore** estão instalados.
    
2. Inicie o **Shell de gerenciamento do Skype for Business Server**.
    
3. Desative o acesso à mobilidade e ligue via trabalho globalmente digitando:
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > Você pode desativar a chamada via trabalho sem desativar o acesso à mobilidade. Mas você não pode desativar a mobilidade sem também desativar a chamada via trabalho. 
  
    Para obter mais informações, confira [set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-site"></a>Modificar política de mobilidade por site

1. Faça logon, com uma conta que seja membro da função **CsAdministrator** , para um computador onde o **Shell de gerenciamento do Skype for Business Server** e o **OCScore** estão instalados.
    
2. Inicie o **Shell de gerenciamento do Skype for Business Server**.
    
3. Você pode criar uma política de nível de site, desativar VoIP e vídeo, habilitar exigir WiFi para áudio IP e exigir WiFi para vídeo IP por site. Tipo:
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    Saiba mais em [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-user"></a>Modificar política de mobilidade por usuário

1. Faça logon, com uma conta que seja membro da função **CsAdministrator** , para um computador onde o **Shell de gerenciamento do Skype for Business Server** e o **OCScore** estão instalados.
    
2. Inicie o **Shell de gerenciamento do Skype for Business Server**.
    
3. Crie políticas de mobilidade de nível de usuário e desative a mobilidade e ligue via trabalho por usuário. Tipo:
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    Um exemplo adicional com dados de exemplo:
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > Você pode desativar a chamada via trabalho sem desativar o acesso à mobilidade. Mas você não pode desativar a mobilidade sem também desativar a chamada via trabalho. 
  

