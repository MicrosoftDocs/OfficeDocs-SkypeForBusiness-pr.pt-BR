---
title: 'Lync Server 2013: Configurar regras de publicação na Web para um único pool interno'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure web publishing rules for a single internal pool
ms:assetid: 86ff4b2a-1ba9-46a2-a175-8b19e00a49dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429712(v=OCS.15)
ms:contentKeyID: 48184725
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ffe61072df14e28c20c45eb72302905986c6357
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a>Configurar regras de publicação na Web para um único pool interno no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-07-07_

Microsoft Forefront Threat Management Gateway 2010 e roteamento de solicitação de aplicativo do Internet Information Server (IIS ARR) usa regras de publicação na Web para publicar recursos internos, como uma URL de reunião, para os usuários da Internet.

Além das URLs de serviços Web para os diretórios virtuais, você também deve criar regras de publicação para URLs simples, a URL LyncDiscover e o Office Web Apps Server. Para cada URL simples, você deve criar uma regra individual no proxy inverso que aponta para essa URL simples.

Se você estiver implantando a mobilidade e usando a descoberta automática, será necessário criar uma regra de publicação para a URL do serviço de descoberta automática externa. A descoberta automática também requer regras de publicação para a URL de serviços Web externos do Lync Server para o pool de directors e para o pool de front-ends. Para obter detalhes sobre como criar as regras de publicação na Web para descoberta automática, consulte Configurando [o proxy reverso para a mobilidade no Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).

Use os procedimentos a seguir para criar regras de publicação na Web.

<div>


> [!NOTE]  
> Esses procedimentos pressupõem que você tenha instalado a edição padrão do Forefront Threat Management Gateway (TMG) 2010 ou instalou e configurou o Internet Information Server com a extensão de roteamento de solicitação de aplicativo (IIS ARR). Você usa a TMG ou a ARR do IIS.



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a>Para criar uma regra de publicação do servidor Web no computador executando o TMG 2010

1.  Clique em **Iniciar**, selecionar **programas**, selecionar **Microsoft Forefront TMG**e, em seguida, clique em gerenciamento do **Forefront TMG**.

2.  No painel esquerdo, expanda **ServerName**, clique com o botão direito do mouse em **política de firewall**, selecione **novo**e clique em regra de **publicação de site da Web**.

3.  Na página **Bem-vindo à nova regra de publicação na Web** , digite um nome para exibição para a regra de publicação (por exemplo, LyncServerWebDownloadsRule).

4.  Na página **Selecionar ação da regra** , selecione **permitir**.

5.  Na página **tipo de publicação** , selecione **publicar um único site da Web ou um balanceador de carga**.

6.  Na página **segurança de conexão do servidor** , selecione **usar SSL para se conectar ao servidor Web ou ao farm de servidores publicado**.

7.  Na página **detalhes da publicação interna** , digite o nome de domínio totalmente qualificado (FQDN) do Web farm interno que hospeda o conteúdo da sua reunião e o conteúdo do catálogo de endereços na caixa **nome do site interno** .
    
    <div>
    

    > [!NOTE]  
    > Se o seu servidor interno for um servidor de edição padrão, esse FQDN será o FQDN do servidor Standard Edition. Se o seu servidor interno for um pool de front-ends, esse FQDN será um VIP (IP virtual) do balanceador de carga de hardware que carrega o balanceamento de servidores internos de Web farm. O servidor TMG deve ser capaz de resolver o FQDN para o endereço IP do servidor Web interno. Se o servidor TMG não conseguir resolver o FQDN para o endereço IP correto, você pode selecionar <STRONG>usar um nome de computador ou endereço IP para se conectar ao servidor publicado</STRONG>e, em seguida, na caixa <STRONG>nome do computador ou</STRONG> <STRONG>endereço IP</STRONG> , digitar o endereço IP do w "interno" servidor da EB. Se fizer isso, você deve garantir que a porta 53 esteja aberta no servidor TMG e que ela possa alcançar um servidor DNS que reside na rede de perímetro. Você também pode usar entradas no arquivo hosts locais para fornecer resolução de nomes.

    
    </div>

8.  Na página **detalhes da publicação interna** , na caixa **caminho (opcional)** , digite ** / ** como o caminho da pasta a ser publicada.
    
    <div>
    

    > [!NOTE]  
    > No assistente de publicação de site, você pode especificar apenas um caminho. Caminhos adicionais podem ser adicionados modificando as propriedades da regra.

    
    </div>

9.  Na página **detalhes do nome público** , confirme se **esse nome de domínio** está selecionado em **aceitar solicitações por**, digite o FQDN dos serviços Web externos, na caixa **nome público** .

10. Na página **selecionar ouvinte da Web** , clique em **novo** para abrir o assistente de definição de novo ouvinte da Web.

11. Na página **Bem-vindo ao novo assistente de ouvinte da Web** , digite um nome para o ouvinte da Web na caixa **nome do ouvinte da Web** (por exemplo, LyncServerWebServers).

12. Na página **segurança de conexão do cliente** , selecione **exigir conexões SSL seguras com clientes**.

13. Na página **endereço IP do ouvinte da Web** , selecione **externo**e clique em **selecionar endereços IP**.

14. Na página **seleção de IP de ouvinte externo** , selecione o **endereço IP especificado no computador Forefront TMG na rede selecionada**, selecione o endereço IP apropriado e clique em **Adicionar**.

15. Na página **certificados SSL** de ouvinte, selecione **atribuir um certificado para cada endereço IP**, selecione o endereço IP associado ao FQDN da Web externa e clique em **Selecionar certificado**.

16. Na página **Selecionar certificado** , selecione o certificado que corresponde aos nomes públicos especificados na etapa 9, clique em **selecionar**.

17. Na página **configuração de autenticação** , selecione **sem autenticação**.

18. Na página **configuração de logon único** , clique em **Avançar**.

19. Na página **concluindo o assistente de ouvinte da Web** , verifique se as configurações do **ouvinte da Web** estão corretas e clique em **concluir**.

20. Na página **delegação de autenticação** , selecione **sem delegação, mas o cliente pode autenticar diretamente**.

21. Na página **conjunto de usuários** , clique em **Avançar**.

22. Na página **concluindo o assistente de nova regra de publicação na Web** , verifique se as configurações da regra de publicação da Web estão corretas e clique em **concluir**.

23. Clique em **aplicar** no painel detalhes para salvar as alterações e atualizar a configuração.

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a>Para criar uma regra de publicação do servidor Web no computador que está executando o IIS ARR

1.  Vincule o certificado que você usará para o proxy reverso para o protocolo HTTPS. Clique em **Iniciar**, selecione **programas**, selecione **Ferramentas administrativas**e, em seguida, clique em **Gerenciador dos serviços de informações da Internet (IIS)**.
    
    <div>
    

    > [!NOTE]  
    > Ajuda adicional, capturas de tela e orientações sobre a implantação e configuração do IIS ARR podem ser encontradas no artigo NextHop <A href="http://go.microsoft.com/fwlink/?linkid=293391">usando o IIS arr como um proxy inverso para o Lync Server 2013</A>.

    
    </div>

2.  Se você ainda não tiver feito isso, importe o certificado que será usado para o proxy inverso. No **Gerenciador dos serviços de informações da Internet (IIS)**, clique no nome do servidor proxy reverso no tamanho esquerdo do console. No meio do console em **IIS** , localize **certificados do servidor**. Clique com o botão direito do mouse em **certificados de servidor** e selecione **abrir recurso**.

3.  No lado direito do console, clique em **importar..**.. Digite o caminho e o nome do arquivo do certificado com a extensão ou clique em **...** para procurar o certificado. Selecione o certificado e clique em **abrir**. Forneça a senha usada para proteger a chave privada (se você tiver atribuído uma senha ao exportar o certificado e a chave particular). Clique em **OK**. Se a importação do certificado tiver sido bem-sucedida, o certificado será exibido como uma entrada no meio do console como uma entrada em **certificados de servidor**.

4.  Atribua o certificado a ser usado por HTTPS. No lado esquerdo do console, selecione o **site da Web padrão** do IIS Server. No lado direito, clique em **associações..**.. Na caixa de diálogo **associações de site** , clique em **Adicionar..**.. Na caixa de diálogo **Adicionar Associação de site** , em **tipo:**, selecione **https**. Selecionar https permitirá que você selecione o certificado que será usado para https. Em **certificado SSL:**, selecione o certificado que você importou para o proxy inverso. Clique em **OK**. Em seguida, clique em **fechar**. O certificado agora está associado ao proxy reverso para Secure Socket Layer (SSL) e Transport Layer Security (TLS).
    
    <div>
    

    > [!IMPORTANT]  
    > Se você receber um aviso ao fechar as caixas de diálogo de associações em que os certificados intermediários estão ausentes, você precisará localizar e importar o certificado de autoridade raiz da CA pública e qualquer certificado intermediário da autoridade de certificação. Consulte as instruções na CA pública para a qual você solicitou o certificado e siga as instruções para solicitar e importar uma cadeia de certificados. Se você exportou o certificado do servidor de borda, poderá exportar o certificado da CA raiz e qualquer certificado de autoridade de certificação intermediário associado ao servidor de borda. Importar o certificado da CA raiz para o computador (não ser confundido com o armazenamento do usuário) armazenamento de autoridades de certificação raiz confiáveis e certificados intermediários no repositório de autoridades de certificação intermediárias do computador.

    
    </div>

5.  No lado esquerdo do console abaixo do nome do servidor IIS, clique com o botão direito do mouse em **farm de servidores** e clique em **criar farm de servidores..**..
    
    <div>
    

    > [!NOTE]  
    > Se você não vir o nó <STRONG>farms de servidores</STRONG> , será necessário instalar o roteamento de solicitação de aplicativo. Para obter detalhes, consulte Configurando <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">servidores proxy reverso para o Lync Server 2013</A>.

    
    </div>
    
    Na caixa de diálogo **criar farm de servidores** no **nome do farm de servidores**, digite um nome (isso pode ser um nome amigável para fins de identificação) para a primeira URL. Click **Next**.

6.  Na caixa de diálogo **Adicionar servidor** no **endereço do servidor**, digite o nome de domínio totalmente qualificado (FQDN) dos serviços Web externos em seu servidor front-end. Os nomes que serão usados aqui para fins de exemplo são os mesmos que são usados na seção de planejamento para o proxy reverso, de [Resumo de certificado-proxy reverso no Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md). Fazendo referência ao plano de proxy reverso, digitamos o `webext.contoso.com`FQDN. Confirme se a caixa de seleção ao lado de **online** está selecionada. Clique em **Adicionar** para adicionar o servidor ao pool de servidores Web para essa configuração.
    
    <div>
    

    > [!WARNING]  
    > O Lync Server usa balanceadores de carga de hardware para o diretor de pools e servidores front-end para tráfego HTTP e HTTPS. Você só vai fornecer um FQDN ao adicionar um servidor ao farm de servidores do IIS ARR. O FQDN será o servidor front-end ou o director em configurações de servidor sem pool ou o FQDN do balanceador de carga de hardware configurado para pools de servidores. O único método suportado para balancear a carga de tráfego HTTP e HTTPS é usando balanceadores de carga de hardware.

    
    </div>

7.  Na caixa de diálogo **Adicionar servidor** , clique em **Configurações avançadas..**.. Isso abre uma caixa de diálogo para definir o roteamento de solicitação de aplicativo para solicitações para o FQDN configurado. O objetivo é redefinir qual porta será usada quando a solicitação for processada pelo IIS ARR.
    
    Por padrão, a porta HTTP de destino deve ser definida como 8080. Clique em ao lado do **httpPort** atual do 80 e defina o valor como **8080**. Clique em ao lado do **httpsPort** atual do 443 e defina o valor como **4443**. Deixe o parâmetro de **peso** em 100. Se necessário, você pode redefinir os pesos de uma determinada regra quando tiver estatísticas da linha de base. Clique em **concluir** para concluir esta parte da configuração da regra.

8.  Você pode ver uma caixa de diálogo regravar regras que informa que o Gerenciador do IIS pode criar uma regra de regravação de URL para direcionar todas as solicitações de entrada para o farm de servidores automaticamente. Clique em **Sim**. Você vai ajustar as regras manualmente, mas selecionar Sim define a configuração inicial..

9.  Clique no nome do farm de servidores que você acabou de criar. Em **farm de servidores** no modo de exibição recursos do Gerenciador do IIS, clique duas vezes em **cache**. Desmarque **Habilitar cache de disco**. Clique em **aplicar** à direita.

10. Clique no nome do farm de servidores. Em **Server farm** in IIS Manager Features View, clique duas vezes em **proxy**. Na página Configurações de proxy, altere o valor de **tempo limite (segundos)** para um valor apropriado para a sua implantação. Clique em **aplicar** para salvar a alteração.
    
    <div>
    

    > [!IMPORTANT]  
    > O valor de tempo limite do proxy é um número que varia de implantação para implantação. Você deve monitorar a implantação e modificar o valor da melhor experiência para os clientes. Talvez seja possível definir o valor tão baixo quanto 200. Se você estiver oferecendo suporte a clientes móveis do Lync em seu ambiente, deve definir o valor como 960 para permitir o tempo limite de notificações por push do Office 365 que têm um valor de tempo limite de 900. É muito provável que você precise aumentar o valor de tempo limite para evitar que o cliente se desconecte quando o valor for muito baixo ou diminuir o número se as conexões pelo proxy não forem desconectadas e muito demoradas após o cliente ter sido desconectado. Monitoramento e alinhamento base o que é normal para o seu ambiente é o único meio preciso para determinar onde está a configuração certa para esse valor.

    
    </div>

11. Clique no nome do farm de servidores. Em **farm de servidores** no modo de exibição recursos do Gerenciador do IIS, clique duas vezes em **regras de roteamento**. Na caixa de diálogo regras de roteamento em roteamento, desmarque a caixa de seleção ao lado de habilitar o carregamento de SSL. Se a capacidade de desmarcar a caixa de seleção não estiver disponível, marque a caixa de seleção **usar URL regravar para inspecionar solicitações de entrada**. Clique em **aplicar** para salvar as alterações.
    
    <div>
    

    > [!WARNING]  
    > Não há suporte para o carregamento de SSL pelo proxy reverso.

    
    </div>

12. Repita as etapas 5-11 para cada URL que deve passar pelo proxy reverso. Uma lista comum seria a seguinte:
    
      - Serviços Web de servidor front-end externo: webext.contoso.com (já configurado pela passagem inicial)
    
      - Serviços Web de diretor externo para Director: webdirext.contoso.com (opcional se um diretor estiver implantado)
    
      - Reunião simples de URL: meet.contoso.com
    
      - URL simples de discagem: dialin.contoso.com
    
      - URL de descoberta automática do Lync: lyncdiscover.contoso.com
    
      - URL do servidor dos Office Web Apps: officewebapps01.contoso.com
        
        <div>
        

        > [!IMPORTANT]  
        > A URL do servidor do Office Web Apps usará um endereço httpsPort diferente. Na etapa 7, você define o <STRONG>httpsPort</STRONG> como <STRONG>443</STRONG> e o <STRONG>httpPort</STRONG> como a porta <STRONG>80</STRONG>. Todas as outras definições de configuração são iguais.

        
        </div>

13. No lado esquerdo do console, clique no nome do servidor IIS. No meio do console, localize a **URL reescrita** no **IIS**. Clique duas vezes em URL reescrever para abrir a configuração de regras de recriação de URL. Você deve ver regras para cada Server farm que você criou nas etapas anteriores. Se você não tiver, confirme se clicou no nome do **servidor IIS** imediatamente abaixo do nó da **página inicial** no console do Gerenciador de servidor de informações da Internet.

14. Na caixa de diálogo de reconfiguração de **URL** , usando webext.contoso.com como exemplo, o nome completo da regra conforme exibido **é\_arr\_webext.contoso.com LoadBalance\_SSL**.
    
      - Clique duas vezes na regra para abrir a caixa de diálogo **Editar regra de entrada** .
    
      - Clique em **Adicionar..** . na caixa de diálogo **condições** .
    
      - Na **condição adicionar** na **entrada de condição:** digite **{http\_host}**. (À medida que você digita, é exibida uma caixa de diálogo que permite que você selecione a condição). em **verificar se a cadeia de caracteres de entrada:** seleção **corresponde ao padrão**. No tipo **\*** de **entrada padrão** . O **caso de ignorar** deve ser selecionado. Clique em **OK**.
    
      - Role a tela para baixo na caixa de diálogo **Editar regra de entrada** para localizar a caixa de diálogo de **ação** . **Tipo de ação:** deve ser definido como **rota para o farm de servidores**, **esquema:** definido como **https://**, **farm de servidores:** definido como a URL à qual essa regra se aplica. Para este exemplo, isso deve ser definido como **webext.contoso.com**. **Caminho:** é definido como **/{R: 0}**
    
      - Clique em **aplicar** para salvar as alterações. Clique em **voltar às regras** para retornar às regras de regravação de URL.

15. Repita o procedimento definido na etapa 14 para cada regra de regravação de SSL que você definiu, uma por URL de farm de servidores.
    
    <div>
    

    > [!WARNING]  
    > Por padrão, as regras HTTP também são criadas e são indicadas pelo nome semelhante às regras de SSL. Para o nosso exemplo atual, a regra HTTP seria nomeada <STRONG>ARR_webext. contoso. com _loadbalance</STRONG>. Nenhuma modificação é necessária para essas regras e eles podem ser ignorados com segurança.

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a>Para modificar as propriedades da regra de publicação na Web no TMG 2010

1.  Clique em **Iniciar**, aponte para **programas**, selecione **Microsoft Forefront TMG**e clique em **Gerenciamento do Forefront TMG**.

2.  No painel esquerdo, expanda **ServerName**e clique em **política de firewall**.

3.  No painel detalhes, clique com o botão direito do mouse na regra de publicação do servidor Web que você criou no procedimento anterior (por exemplo, LyncServerExternalRule) e, em seguida, clique em **Propriedades**.

4.  Na página **Propriedades** , na guia **de** , faça o seguinte:
    
      - Na lista **esta regra se aplica ao tráfego dessas fontes** , clique em **qualquer lugar**e, em seguida, clique em **remover**.
    
      - Clique em **Adicionar**.
    
      - Em **adicionar entidades de rede**, expanda **redes**, clique em **externo**, clique em **Adicionar**e, em seguida, clique em **fechar**.

5.  Na guia **para** , certifique-se de que a caixa de seleção **encaminhar o cabeçalho original do host, em vez da opção atual** está marcada.

6.  Na guia **ponte** , marque a caixa de seleção redirecionar **solicitação para porta SSL** e especifique a porta **4443**.

7.  Na guia **nome público** , adicione as URLs simples (por exemplo, meet.contoso.com e Dialin.contoso.com).

8.  Clique em **aplicar** para salvar as alterações e, em seguida, clique em **OK**.

9.  Clique em **aplicar** no painel detalhes para salvar as alterações e atualizar a configuração.

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a>Para modificar as propriedades da regra de publicação na Web no IIS ARR

1.  Clique em **Iniciar**, selecione **programas**, selecione **Ferramentas administrativas**e, em seguida, clique em **Gerenciador dos serviços de informações da Internet (IIS)**.

2.  No lado esquerdo do console, clique no nome do servidor IIS.

3.  No meio do console, localize a **URL reescrita** no **IIS**. Clique duas vezes em URL reescrever para abrir a configuração de regras de recriação de URL.

4.  Clique duas vezes na regra que você precisa modificar. Faça suas modificações, conforme necessário, em **correspondência URL**, **condições**, **variáveis do servidor** ou **ação**.

5.  Clique em **aplicar** para confirmar as alterações. Clique em **retornar às regras** para modificar outras regras ou fechar o console do **Gerenciador do IIS** se você tiver concluído suas alterações.

</div>

</div>

<span> </span>

</div>

</div>

</div>

