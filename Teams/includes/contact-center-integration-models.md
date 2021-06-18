## <a name="integration-models-for-solution-providers"></a>Modelos de integração para provedores de soluções

<a name="steps"></a>

Como provedor de soluções de central de contatos, há três modelos a escolher para integrar sua solução de central de contatos conectada ao Teams:

- Se você quiser usar SBCs certificados e Roteamento Direto para conectar uma solução de central de contatos ao Teams, consulte o [modelo Connect](?tabs=connect#steps).

- Se você quiser usar bots do Azure e as APIs de Comunicação do Microsoft Graph para habilitar provedores de soluções para criar aplicativos do Teams, consulte o modelo [extend](?tabs=extend#steps).

- Se você quiser usar um SDK que habilita os provedores de soluções a compartilhar experiências nativas do Teams em seu Aplicativo, consulte o [modelo power](?tabs=power#steps). As soluções de energia serão possíveis quando o SDK estiver disponível, no final de 2021.

### <a name="the-connect-model"></a>[**O modelo Connect**](#tab/connect)

O modelo Connect usa SBCs certificados pela Microsoft e Roteamento Direto para conectar soluções de contact center à infraestrutura do sistema de telefonia do Teams, habilitando o roteamento, a configuração e as percepções do sistema aprimoradas.

Os agentes podem configurar assistentes virtuais automatizados e filas de roteamento baseadas em habilidades para coletar informações e conectar clientes com especialistas no assunto.

**Destaques do recurso:**

Embora esses recursos não sejam uma lista abrangente de recursos para esse modelo de integração, as áreas de foco incluem:

  - AuthN do Office 365 para que os agentes se conectem ao locatário da Microsoft a partir do cliente CCaaS integrado 

  - Veja quando os agentes estão disponíveis com o Teams

  - Transferências e suporte a chamada de grupo com o Teams 

  - APIs do Teams Graph e APIs de Comunicação na Nuvem para integração com o Teams 

  - Tronco SIP de vários locatários para dar suporte a vários clientes no SBC do provedor de soluções.  

  - Provedores de soluções para usar o [ <span class="underline">controlador de borda de sessão certificado pela Microsoft (SBC)</span>](../direct-routing-border-controllers.md)


### <a name="the-extend-model"></a>[**O modelo Extend**](#tab/extend)

O modelo Extend se integra ao cliente do Teams usando a plataforma cliente [do Teams,](/microsoftteams/platform/overview) [APIs do Teams Graph](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) e API de [Comunicações na Nuvem no Microsoft Graph.](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) O modelo Extend também usa o sistema de telefonia do Teams para todas as chamadas e experiências de controle de chamadas da central de contatos, e o provedor de soluções do centro de contatos atua como uma operadora de telefonia juntamente com o Microsoft 365.

Os agentes podem usar o Teams para colaboração interna e comunicação externa e podem se beneficiar de notas contextuais dinâmicas correlacionando dados de vários sistemas antes de iniciar um envolvimento e, em seguida, evitar a alternência de contexto custosa.

As organizações podem projetar fluxos de trabalho e configurações de roteamento avançadas para o indivíduo e medir a qualidade de seu sistema e interações.

**Destaques do recurso:**

Embora esses recursos não sejam uma lista abrangente de recursos para esse modelo de integração, as áreas de foco incluem:

  - APIs do Teams Graph e APIs de Comunicação na Nuvem para integração com o Teams 

  - Aplicativo baseado no Teams para experiências de agente 

  - Teams como o ponto de extremidade de chamada principal para os agentes 

  - Cliente teams chamando todos os controles de chamada

  - Aplicativo de experiência de agente para cliente web e móvel do Teams

  - Análise, gerenciamento de fluxo de trabalho, experiências baseadas em função para agentes no aplicativo CCaaS no Teams

  - Experiências de chat e colaboração integradas aos clientes do Teams 

  - Preservar o desempenho e a qualidade das experiências do cliente do Teams em todos os aplicativos  

### <a name="the-power-model"></a>[**O modelo Power**](#tab/power)

O modelo Power permite que provedores de soluções criem aplicativos de voz nativos baseados no Azure usando a infraestrutura de chamadas do Teams e a plataforma de cliente para fornecer soluções modernas e inteligentes para conexão colaborativa de cliente e agente. O objetivo do modelo Power é fornecer uma experiência de central de contatos de um aplicativo com uma tela.

**Destaques do recurso:**

Embora esses recursos não sejam uma lista abrangente de recursos para esse modelo de integração, as áreas de foco incluem:

  - Experiências de agente formais habilitadas de forma nativa para comunicação omnicanal por meio do SDK do Teams 

  - Usar os serviços de colaboração do Teams para colaboração de agentes e interações do cliente  

  - Provisionamento rápido de serviços de nuvem, implantar em qualquer lugar 

  - Controle de conversa direta e interação com usuários durante conversas do Teams 

>[!NOTE]
> O modelo Power estará disponível no final de 2021.
