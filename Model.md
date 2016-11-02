# add-textbox-dynamically
add-textbox dynamically in asp.net mvc
Otranzao ny code any @Models: ACTIVITES_POSTE

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

