Otranzao ny code any @model:
ACTIVITES_POSTE:

    using System;
    using System.Collections.Generic;
    
    public partial class ACTIVITES_POSTE
    {
        public ACTIVITES_POSTE()
        {
            this.DESCRIPTION = new HashSet<DESCRIPTION>();
        }
    
        public short ID_ACTIVITE { get; set; }
        public string ACTIVITES_ENCADREMENT { get; set; }
        public string ACTIVITE_PRINCIPALES { get; set; }
    
        public virtual ICollection<DESCRIPTION> DESCRIPTION { get; set; }
    }

DESCRIPTION:

    using System;
    using System.Collections.Generic;
    using HtmlHelpers.BeginCollectionItem;
    
    public partial class DESCRIPTION
    {
        public DESCRIPTION()
        {
            this.AGENT = new HashSet<AGENT>();
        }
    
        public short ID_DESCRIPTION { get; set; }
        public string TYPE { get; set; }
    
        public virtual ACTIVITES_POSTE ACTIVITES_POSTE { get; set; }
     }
