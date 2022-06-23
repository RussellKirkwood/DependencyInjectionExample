# DependencyInjectionExample C#
Dependency Injection Example C#

public interface IVehicleType
    {
        void Start();
    }

    public class MotorCycle : IVehicleType
    {
        public void Start()
        {
            Console.WriteLine("Started a MotorCycle");
        }
    }

    public class Car : IVehicleType
    {
        public void Start()
        {
            Console.WriteLine("Started a Car");
        }
    }

    public class Vehicle
    {
        private readonly IVehicleType _vehicle;
        public Vehicle(IVehicleType vehicle)
        {
            _vehicle = vehicle;
        }

        public void Run()
        {
            _vehicle.Start();
        }
    }
    
    
    // Implementation
   Vehicle myCar = new Vehicle(new Car());
   myCar.Run();
   
   Vehicle myMotorCycle = new MotorCycle(new MotorCycle());
   myMotorCycle.Run();
N
